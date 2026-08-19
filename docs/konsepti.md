# Konsepti

## 1. Ongelma

Teknisen tapahtumatuotannon vaikein ongelma ei ole kalustohallinta. Se on kääntäminen.

Asiakas puhuu tapahtumasta: "tarvitaan näyttävä avajaispuhe ja striimi".
Tekniikka elää patchissa, riderissa, virrankulutuksessa, kaapelipituuksissa ja
miehityksessä. Näiden välissä on tuottaja, joka kääntää käsin.

Käännöstyö tapahtuu tänään sähköpostiketjuissa, WhatsAppissa, Excel-kuormalistoissa
ja Drive-kansiossa, jossa on neljätoista versiota pohjakuvasta. Tuottajan ajasta
merkittävä osa ei mene tuottamiseen vaan tiedon perässä juoksemiseen ja sen
selvittämiseen, mistä oikeastaan sovittiin.

## 2. Markkina-aukko

Olemassa olevat työkalut ratkaisevat jomman kumman pään, eivät väliä.

**Vuokrausjärjestelmät** (Rentman, Current RMS, HireHop) ovat kalustorekisteri ensin.
Asiakasnäkymä on niissä käytännössä tarjous-PDF.

**AV-integraattoreiden myyntityökalut** (Jetbuilt, D-Tools) ovat kiinteiden
asennusten CPQ:ta. Ne mallintaa järjestelmän, eivät tapahtumaa, jolla on aikataulu.

**Projektinhallintatyökalut** (ClickUp, Notion, Monday) ovat sisäisiä. Asiakasta ei
saa sinne, eikä pitäisikään saada.

Asiakasrajapinta on kaikilla se osa, joka jätettiin viimeiseksi. Siinä on aukko.

Ja aukolla on syy: brief-to-rider-käännös vaati aiemmin aina ihmistuottajan, joten
tällaista alustaa ei kannattanut rakentaa. Se on nyt ensimmäistä kertaa
realistista automatisoida luonnostasolla.

## 3. Periaatteet

### 3.1 Yksi linkki per tapahtuma

Asiakas ei kirjaudu järjestelmään, ei opettele työkalua, ei saa tunnuksia.
Hän saa yhden pysyvän osoitteen, joka **on** se tapahtuma: brief, tarjous,
aikataulu, yhteystiedot, pohjakuvat, muutokset, ja tapahtuman jälkeen loppuraportti
ja lasku.

Jokainen ylimääräinen portaali, johon asiakkaan pitäisi muistaa erikseen mennä,
on kuollut ominaisuus. Todellinen kilpailija ei ole toinen ohjelmisto. Se on sähköposti.

### 3.2 Kaksi näkymää samaan dataan

Tämä on koko homman ydin ja ainoa vaikea osa.

Sama tietomalli renderöityy sisäisesti tekniikkana (patch, kuormalista, ajolista,
virtalaskelma, työvuorot) ja asiakkaalle luettavasti ("lavalla 3 langatonta mikkiä,
LED-seinä 6x3 m, kuva tulee tästä").

Ei kahta dokumenttia, joita synkataan käsin. Kun tekniikka muuttuu, asiakkaan näkymä
muuttuu automaattisesti, ja päinvastoin.

### 3.3 Taso ilmestyy vasta kun sitä on kaksi

Yhden lavan tuotannossa sanaa "lava" ei näy käyttöliittymässä lainkaan, koska
navigoitavaa tasoa ei ole. Kun toinen lava lisätään, lavataso muuttuu navigoitavaksi
ja sisältö siirtyy sen alle automaattisesti.

Ei tilaa, jossa käyttäjä valitsee "yksinkertaisen" ja "edistyneen" tilan väliltä.
Monimutkaisuus ilmestyy siksi, että data vaatii sitä.

### 3.4 Kaikki muut ehdottavat

Ainoa oikeus, jolla on oikeasti merkitystä, ei ole muokkausoikeus. Se on oikeus
sitoa rahaa.

Kaikki muut tekevät ehdotuksia. Ehdotus ei ole muutos. Se menee muutoslokiin tilassa
"pyydetty" ja odottaa hyväksyntää siltä, jolla on mandaatti. Tästä seuraa, että
pääsyn kanssa voi olla antelias: kukaan ei riko tapahtumaa sillä, että hänellä on linkki.

### 3.5 Ydin on deterministinen

Virrankulutus, painot, riggauskuormat, DMX-universumit, heittoetäisyydet,
kaapelipituudet ja kaluston saatavuus lasketaan koodilla. Ei kielimallilla.
Tässä ei ole harmaata aluetta.

## 4. Toiminnallinen ydin

### 4.1 Brief kysyy kuin ihminen

Vastaus avaa seuraavat kysymykset: onko puhetta, onko musiikkia, striimataanko,
montako esiintyjää, minkälainen tila. Lopputulos on koneluettava tarvekartta,
joka mappautuu kalustopaketteihin ja tuntiarvioihin.

### 4.2 Tarjous on elävä, ei PDF

Riveillä vaihtoehdot (perus / suositus / maksimi). Asiakas klikkaa ja näkee sekä
hinnan että teknisen seurauksen samassa hetkessä. Hyväksyntä kohdistuu versioon,
ja versiot säilyvät.

### 4.3 Muutosloki on tuote, ei sivutuote

Suurin osa riidoista on muotoa "eikös sovittu että". Jokaisesta muutoksesta jää:
kuka pyysi, milloin, mitä maksoi, mihin vaikutti. Asiakas näkee saman lokin samasta
linkistä. Lopussa lasku kirjoittaa itsensä lokista, eikä sitä tarvitse perustella.

### 4.4 Aikataulu, jossa on riippuvuudet

Asiakas muokkaa ohjelmaa, järjestelmä siirtää soundcheckin, fokuksen, kasauksen ja
kutsuajat. Kun ovet siirtyvät puoli tuntia, se näkyy heti myös miehityskuluissa.

### 4.5 Järjestelmä jahtaa asiakasta, ei tuottaja

Alusta tietää mitä tarvitsee ja milloin: rider T-14, lopullinen ohjelma T-3,
esitysgrafiikat T-1. Muistutukset lähtevät automaattisesti.

Tämä on se osa, joka oikeasti palauttaa tuottajalle tunteja viikossa.

### 4.6 Tiedostoilla on paikka ja validointi

Ei Drive-kansiota, vaan nimetyt paikat: esitysgrafiikat, artistin rider, pohjakuva.
Jokaisella paikalla on omistaja, määräaika ja tekniset vaatimukset. Väärä resoluutio
tai kuvasuhde hylätään latausvaiheessa, ei lavalla.

### 4.7 Keikkapäivänä näkymä romahtaa

Puhelin, pimeä halli, huono verkko. Näkyviin jää: mikä on seuraavaksi, kuka on missä,
yksi soittonappi, ja ongelmanappi joka ohjautuu oikealle ihmiselle. Offline-first.

Isossa tuotannossa sama näkymä kääntyy ympäri: kysymys ei ole "mitä seuraavaksi"
vaan "mikä on rikki, missä, ja kuka on vapaana".

### 4.8 Jälkihoito tekee toistosta helppoa

Automaattinen kooste: mitä toimitettiin, mikä meni pieleen, mitä ensi kerralla toisin.
Se on samalla ensi vuoden pohja. Toistuvat tapahtumat ovat se, missä raha on.

## 5. Tekoälyn rooli

Malli kuuluu alustan reunoille, ei ytimeen. Sisään- ja ulostuloissa kielimalli,
välissä tavallinen tylsä deterministinen sovellus.

Neljä paikkaa, joissa se ansaitsee tilansa:

1. **Riderien lukeminen.** Artistien PDF-riderit ovat jokainen omanlaisensa.
   Malli purkaa niistä input-listan, monitorointitarpeet, backlinen ja virrantarpeen
   rakenteiseksi dataksi. Dokumenttien poimintaa, jossa virheen näkee heti.
2. **Briefin muuttaminen tarvekartaksi.** Vapaasta tekstistä ehdotus kalustopaketiksi,
   miehitykseksi ja tuntiarvioksi. Luonnos, jonka ihminen hyväksyy.
3. **Käännös toiseen suuntaan.** Tekninen data asiakkaan kielelle automaattisesti.
   Matala riski, iso hyöty, helppo tarkistaa.
4. **Viestien muuttaminen muutoksiksi.** Asiakkaan sähköposti muuttuu ehdotetuksi
   riviksi muutoslokiin kustannusvaikutuksineen. Tässä jäsentymätön viestintä muuttuu
   rakenteiseksi dataksi, eli tapahtuu se, mihin koko alusta perustuu.

Myöhemmin, kun dataa on kertynyt: **arvioiden kalibrointi omasta historiasta.**
Enemmän analytiikkaa kuin tekoälyä, mutta malli auttaa tunnistamaan mikä tapahtuma
on vastaava.

### Mihin sitä ei laiteta

- Chatbotiksi asiakasrajapintaan. Asiakas haluaa nähdä oman tapahtumansa, ei
  keskustella siitä.
- Mihinkään, joka lähtee ulos ilman ihmistä: ei automaattisia tarjouksia,
  hyväksyntöjä eikä tilauksia alihankkijoille.
- Laskentaan. Katso 3.5.

### Luottamuksen ehto

Jokainen mallin tuottama asia menee sisään luonnoksena, jolla on jäljitettävä lähde.
Ehdotettu kalustorivi linkittyy siihen lauseeseen briefissä tai riderissa, josta se tuli.
Muutosloki näyttää kuka ehdotti ja kuka hyväksyi.

Tässä alassa yksi väärä kalustorivi on pilalla mennyt show. Luottamus ei synny
tarkkuudesta vaan siitä, että virheen näkee ennen kuin se maksaa.

## 6. Skaalautuvuus

**Festivaali ei ole iso tapahtuma. Se on monta pientä tapahtumaa, jotka jakavat infran.**

Siksi perusyksikkö ei ole "tapahtuma" vaan kolmiportainen rakenne: tuotanto, paikka, slot.
Tunnin tilaisuus on yksi tuotanto, yksi paikka, yksi slot. Viikon festivaali on yksi
tuotanto, kuusi lavaa, neljäsataa slottia ja kerros jaettuja resursseja. Sama objekti,
eri määrä rivejä. Yksityiskohdat: [tietomalli.md](tietomalli.md).

Rakennusjärjestys tästä: **mallinna festivaali, julkaise pieni.** Jos rakentaa pienen
tapauksen ja liimaa festivaalin päälle, sen kirjoittaa uusiksi. Toisin päin se toimii.

### Mikä oikeasti muuttuu koossa

| | Pieni | Iso |
| --- | --- | --- |
| Asiakas | Yksi taho | Tilaaja plus kymmeniä vastapuolia, jotka eivät maksa mutta vaativat |
| Määräaika | Päivämäärä | Suppilo ja mittari: 143/200 sisässä |
| Muutos | Puhelinsoitto | Kaskadi vaihtoihin, vuoroihin, kuljetuksiin |
| Keikkapäivä | "Mitä seuraavaksi" | "Mikä on rikki ja kuka on vapaana" |
| Toisto | Koko tapahtuma kopioidaan | Infra ja lavat kopioidaan, ohjelma vaihtuu |

### Taloudellinen huomio

Pienessä tilaisuudessa kate on ohut, joten työkalu ei saa maksaa enempää kuin se
säästää ja tarjouksen pitää syntyä minuuteissa. Se tarkoittaa valmiita paketteja,
ei tyhjää lomaketta.

Iso tuotanto maksaa oikeaa rahaa ja siellä on tuotantotoimisto, joka jaksaa opetella.

Eli pienet keikat luovat tavan ja kerryttävät datan, isot maksavat. Sama tuote,
eri rooli liiketoiminnassa.

Myös tekoälyn painopiste kääntyy koon mukaan: pienessä arvo on briefin muuttamisessa
tarjoukseksi, isossa riderien lukemisessa ja karhuamisessa.

## 7. Osapuolet ja päätöksenteko

Roolimatriisi ja oikeustaulukko ovat tässä domainissa väärä ratkaisu. Sidosryhmät ovat
kertaluontoisia ja lyhytikäisiä: tilan vahtimestari, artistin tuotantopäällikkö,
markkinointi-ihminen joka tarvitsee vain LED-seinän mitat, turvallisuuspäällikkö joka
tarvitsee vain purkuajat. Näitä ei voi määritellä etukäteen. Jos ihmisen lisääminen
vaatii roolin konfiguroinnin, tuottaja lähettää sen sähköpostin.

### 7.1 Pääsy seuraa kohdetta, ei ihmistä

Kenellekään ei anneta roolia tuotannossa. Hänelle annetaan linkki johonkin: tähän
lavaan, tähän slottiin, tähän aikatauluun, tähän tiedostopaikkaan. Näkymän määrää
kohde. Näin roolimatriisia ei tarvita, koska rajaus tulee objektipuusta.

Käytännössä: "jaa tämä" siitä näkymästä jossa olet. Ei tunnuksia, ei kutsuprosessia,
ei tilin luontia. Vanheneva linkki.

### 7.2 Mandaatilla on katto, ei totuusarvo

Asiakkaan projektipäällikkö saa hyväksyä muutoksia johonkin summaan asti, sen yli
mennään esimieheen. Se on luku, ei rooli. Näin tapahtuu jo nyt sähköpostissa,
huonosti ja jälkikäteen.

### 7.3 Vaikein ongelma ei ole kuka saa päättää

Se on kuka päättää ja milloin.

Tuotannoissa harvoin kaatuu mikään siihen, että väärä ihminen teki muutoksen.
Ne kaatuvat siihen, että päätöstä ei tehnyt kukaan ja se valui T-1:een, jossa se
maksaa moninkertaisesti.

Siksi jokaisella päätöskohdalla on kolme asiaa: **nimetty päättäjä, määräaika, ja
oletus joka laukeaa jos kukaan ei päätä.** Esimerkiksi: jos ohjelmaa ei ole vahvistettu
T-3 mennessä, ajetaan versio 4 ja sen jälkeiset muutokset laskutetaan erikseen.

Oletus on tässä se voimakas osa. Se tekee muistutuksista legitiimejä eikä nalkuttavia,
ja siitä tulee sopimusteksti, joka on kaikkien nähtävillä koko ajan.

### 7.4 Läpinäkyvyys vähentää työtä, yhdellä rajauksella

Kun pyytäjä näkee, että hänen lisäpyyntönsä maksaa ja vaatii tilaajan hyväksynnän,
osa pyynnöistä katoaa itsestään. Eli oman pyynnön kustannusvaikutus näkyy aina
pyytäjälle.

Kokonaisbudjetti ja kate näkyvät vain niille, joilla on rahamandaatti. Tämä raja
piirretään tarkasti: tilaaja ei halua alihankkijoiden näkevän kokonaisuutta.

## 8. Mitä ei rakenneta

- Käyttäjähallintaa, kutsuprosesseja ja tilejä sidosryhmille
- Roolimatriisia asetuksiin
- Yleistä kommentointia ja keskusteluketjuja. Keskustelu kiinnittyy aina ehdotukseen,
  muuten olet rakentanut chatin ja menettänyt rakenteen
- Kalustorekisteriä. Se on olemassa oleva, ratkaistu ongelma, ja siihen integroidutaan
- Erillistä festivaalituotetta ja pientuotetta. Sama koodi, sama malli
- Chatbottia asiakkaalle
