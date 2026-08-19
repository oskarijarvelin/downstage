# Tiedostot

## Lähtökohta

**Jaettu tiedosto on epäonnistumisen merkki, ei ominaisuus.**

Aina kun jokin asia muuttuu tiedostoksi, jota kaksi osapuolta muokkaa, se karkaa
tietomallista. Sitä ei voi validoida, se ei aja aikataulua, se ei tuota riviä
muutoslokiin eikä sitä voi renderöidä kahdella tavalla. Se on täsmälleen se ongelma,
jonka takia Drive-kansiossa on neljätoista versiota pohjakuvasta.

Siitä seuraa sääntö:

> **Jos kaksi osapuolta muokkaa samaa asiaa, se ei ole tiedosto vaan tietue.**

Ohjelma-aikataulu on selkein esimerkki. Sillä hetkellä kun tilaaja saa ladata
`ohjelma_v7_FINAL.xlsx` työskentelyversioksi, alusta on hävinnyt sähköpostille.

Tiedostoja ei kuitenkaan voi kieltää, koska tilaaja lähettää sen Excelin joka
tapauksessa. Oikea kanta ei ole "ei tiedostoja" vaan:

> **Tiedosto on sisääntulo, ei säilytysmuoto.**

## Kolme luokkaa

Tiedostot eivät ole yksi asia. Ne ovat kolme asiaa, jotka käyttäytyvät eri tavoin.

| Luokka | Esimerkkejä | Mitä tapahtuu |
| --- | --- | --- |
| **1. Lähdemateriaali** | Rider, ohjelma-Excel, tarjouspyyntö | Parsitaan tietueiksi, alkuperäinen säilyy muuttumattomana lähteenä |
| **2. Media-aineisto** | Logo, esitysgrafiikka, video, biisilista | Täyttää nimetyn `toimitettava`-paikan, validoidaan, ei parsita |
| **3. Tuotokset** | Ajolista, patch, kuormalista, tarjous | Ei säilytetä tiedostoina, renderöidään datasta pyydettäessä |

Vain luokka 1 muuttuu tietueiksi. Logon lataaminen ei synnytä yhtään riviä mihinkään,
se vain muuttaa yhden paikan tilan.

## Luokka 1: parsinta ja diff

Sama parsintaputki ajetaan aina. **Tuotannon tila ratkaisee, mitä ulos tulee.**

**Ennen vahvistusta** parsinta tuottaa `tarve`-rivejä tilassa `ehdotettu`. Tuottaja
käy ne läpi ja vahvistaa. Kustannusvaikutusta ei lasketa, koska mitään ei ole vielä
sovittu.

**Vahvistuksen jälkeen** parsinta diffataan olemassa olevia tietueita vasten, ja
erotus tulee ulos `muutos`-riveinä kustannusvaikutuksineen.

Eli sama toiminto muuttuu muutospyynnöksi automaattisesti sillä hetkellä, kun
tuotanto vahvistetaan. Tätä ei tarvitse konfiguroida eikä käyttäjän tarvitse tietää
siitä.

### Miksi tämä on koko luvun tärkein kohta

Kun artisti lähettää riderin version 2, se ei korvaa mitään hiljaa. Se synnyttää
päätettäviä rivejä hintalappuineen sinä päivänä, kun se lähetettiin.

Juuri tässä kohtaa tapahtuvat tänään ne kalleimmat yllätykset: rider-päivitys hukkuu
sähköpostiin ja ilmestyy kasauspäivänä kahtena puuttuvana langattomana.

### Lataaminen ei ole koskaan päätös

Lataaminen on täysin symmetristä. Tuottaja, tilaaja ja vastapuolet käyttävät samaa
mekanismia, ja kenen tahansa lataus voi synnyttää ehdotuksia. Myös tuottajan oma.

Epäsymmetria on vain hyväksynnässä. Vastapuoli voi ladata riderin, joka ehdottaa
merkittävää lisäystä, mutta sen hyväksyy tilaaja mandaattikattonsa rajoissa.
Sama periaate kuin muuallakin: kaikki muut ehdottavat, ja vain rahamandaatti sitoo.

### Kun parsinta epäonnistuu

Malli ei aina osaa lukea tiedostoa. Silloin se ei saa epäonnistua hiljaa eikä
arvata. Tiedosto jää `lahde_dokumentti`-riviksi tilaan `parsimatta` ja tuottajalle
syntyy tehtävä, jossa tiedosto on liitteenä. Käsin tehty parsinta on hyväksyttävä
lopputulos. Väärä automaattinen parsinta ei ole.

Identtinen uudelleenlataus tunnistetaan tiivisteestä eikä tuota mitään.

### Parsinta onnistuu osittain useammin kuin kokonaan epäonnistuu

Yksi lataus ei ole yksi lopputulos. Sama lähetys voi sisältää luettavan riderin ja
skannatun backline-liitteen, josta ei saa tekstiä irti.

**Luettavasta osasta syntyneet rivit etenevät normaalisti eivätkä jää odottamaan
sitä osaa, joka vaatii käsin lukemista.** Muuten yksi huono liite jäädyttäisi koko
latauksen, ja käytännössä tuottaja alkaisi kiertää järjestelmää sähköpostilla.

Dokumentin tila on tällöin `osittain_parsittu`. Tuottajalle syntyy tehtävä vain
siitä osasta, jota malli ei lukenut, ja lataajalle näkyy sama tieto: mikä meni läpi
ja mikä odottaa käsittelyä.

## Luokka 2: aikasidonnainen versiointi

Media-aineisto menee nimettyyn paikkaan, jolla on omistaja, määräaika ja tekniset
vaatimukset. Validointi tapahtuu latausvaiheessa: väärä kuvasuhde tai resoluutio
hylätään silloin, ei lavalla.

Versiointiin tulee aikasidonnainen sääntö:

> **Ennen määräaikaa korvaava lataus on hiljainen. Määräajan jälkeen se on muutos,
> joka menee lokiin.**

Grafiikan vaihtaminen kaksi viikkoa ennen on ilmaista. Sen vaihtaminen kasauspäivänä
maksaa jonkun aikaa, ja silloin se kuuluu lokiin siinä missä mikä tahansa muu pyyntö.

Vanhat versiot säilyvät. Ne eivät näy käyttöliittymässä ilman erillistä pyyntöä,
mutta ne ovat olemassa, koska "mikä versio ajettiin" on kysymys johon pitää pystyä
vastaamaan jälkikäteen.

## Luokka 3: tuotokset ja vanhentunut paperi

Ajolista, patch, kuormalista ja tarjous renderöidään datasta pyydettäessä.
PDF on tuloste, ei totuus.

Tästä seuraa ominaisuus, jota kukaan ei rakenna mutta joka on keikkapäivänä oikeasti
tärkeä:

> **Alusta tietää, kuka latasi tai tulosti minkä version ja milloin.**

Joku tulosti ajolistan kello 14. Kello 20 hän toimii sen mukaan, vaikka väliin on
tullut kaksi muutosta. Kun alusta tietää sen, se voi kertoa siitä sekä hänelle että
tuottajalle. Halpa toteuttaa, ja estää juuri sen tyyppisen virheen, joka näkyy
yleisölle.

## Pohjakuva: ainoa rehellinen poikkeus

Pohjakuva on aito graafinen artefakti, jota molemmat osapuolet piirtävät päälle,
eikä sitä voi mallintaa tietueina ensimmäisessä versiossa.

Ratkaisu on jakaa se kahtia:

- **Kuva** on luokan 2 validoitu liite ja pelkkä tausta
- **Merkinnät ovat dataa sen päällä**: tietueita, joilla on koordinaatit ja viittaus
  slottiin tai tarpeeseen

Näin merkinnät päätyvät muutoslokiin normaalisti ja kuva pysyy vaihdettavana
taustana. Uusi versio pohjakuvasta ei hukkaa merkintöjä, vaan merkitsee ne
tarkistettaviksi.

## Tallennus ja pääsy

Bitit menevät object storageen, eivät tietokantaan.

Pääsy kulkee saman `paasy`-mallin läpi kuin kaikki muukin: allekirjoitettu, vanheneva
URL per pääsyrivi. Ei julkisia bucket-osoitteita missään olosuhteissa, koska riderit,
sopimukset ja yhteystiedot ovat luottamuksellisia ja linkit vuotavat eteenpäin aina.

## Mitä ei hostata

LED-sisällöt ja taustavideot ovat kymmeniä gigoja. **Alusta ei ole
tiedostonsiirtopalvelu, eikä siitä yritetä tehdä sellaista.**

Realistinen kanta: metadata, tekniset vaatimukset, määräaika ja vastaanoton kuittaus
alustalla, isot bitit siellä missä ne jo liikkuvat. Alustalla on linkki ja tieto siitä,
että tiedosto on haettu ja tarkistettu.

Yritys hostata 200 gigan LED-sisältöä tappaa MVP:n ennen vaihetta 1.

## Mitä ei rakenneta

- **Kansiopuuta tai tiedostoselainta.** Jos alustassa on kansiopuu, olet rakentanut
  Driven ja hävinnyt. Jokainen tiedosto kiinnittyy johonkin objektiin, ja se on ainoa
  tapa löytää se.
- **Selaimessa muokattavia dokumentteja.** Jos jokin asia vaatii yhteismuokkausta,
  se on merkki siitä että asia kuuluu tietueiksi, ei tiedostoksi.
- **Yleistä versiohistoriaselainta.** Versiot säilyvät, mutta niiden selaaminen ei
  ole käyttötapaus. Kysymys on aina "mikä oli voimassa silloin", ja siihen vastaa
  muutosloki.

## Avoin kysymys: rivien tunnistaminen versioiden välillä

Diff toimii vain, jos tarpeet osataan tunnistaa samoiksi eri dokumenttiversioiden
välillä. Muuten riderin versio 2 näyttää siltä, että kaikki poistettiin ja kaikki
lisättiin uudestaan, ja muutosloki täyttyy roskasta.

Kandidaatit: tunnistus kategorian ja kuvauksen samankaltaisuuden perusteella,
tai mallin tekemä eksplisiittinen vastaavuuden ehdotus, jonka ihminen korjaa.
Jälkimmäinen on todennäköisesti oikein, koska se sopii samaan kaavaan kuin kaikki
muukin: malli ehdottaa, ihminen vahvistaa.

Tämä pitää ratkaista ennen vaihetta 5. Katso [mvp.md](mvp.md).
