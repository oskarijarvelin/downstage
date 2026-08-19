# Prompti: asiakas- ja tuottajanäkymä

Syöte Claude Designille. Liitä repo mukaan konteksiksi, jotta se lukee `docs/`.

---

## Konteksti

Suunnittele kaksi näkymää tuotteesta nimeltä **Downstage**, joka on teknisen
tapahtumatuotannon asiakasrajapinta.

Lue ensin tämän repon `docs/konsepti.md`, `docs/tietomalli.md` ja
`docs/tiedostot.md`. Ne ovat totuus. Jos alla oleva ohje on ristiriidassa niiden
kanssa, dokumentit voittavat, ja kerro ristiriidasta.

Tuotteen ydinväite yhdellä lauseella: **sama data renderöityy kahdesti, teknisenä
tuottajalle ja asiakkaan kielellä tilaajalle.** Näiden kahden mockupin tehtävä on
tehdä tuo väite näkyväksi. Sama tuotanto, sama totuus, kaksi täysin eri
käyttöliittymää.

## Suunniteltavat näkymät

**A. Asiakasnäkymä.** Yksi jaettu linkki, jonka tilaaja avaa. Työpöytä ja puhelin.

**B. Tuottajan näkymä.** Sama tuotanto sisältäpäin. Vain työpöytä.

## Esimerkkidata

Käytä täsmälleen tätä keksittyä tuotantoa molemmissa näkymissä, jotta ne voi
asettaa vierekkäin. Kaikki nimet ja summat ovat kuvitteellisia.

**Tuotanto:** Kevätgaala 2027
**Tilaaja:** Nordkraft Oy
**Paikka:** Juhlasali (yksi paikka)
**Päivä:** keskiviikko 14.4.2027
**Tilaajan yhteyshenkilö:** Marja Lehtinen, projektipäällikkö, mandaattikatto 1 500
**Eskalointi:** Timo Rasi, markkinointijohtaja

### Aikataulu

| Klo | Mitä | Näkyy asiakkaalle |
| --- | --- | --- |
| 08:00 | Kasaus alkaa | kyllä |
| 13:00 | Äänen soundcheck | ei |
| 15:00 | Bändin soundcheck | kyllä |
| 16:30 | Puhujan läpimeno | kyllä |
| 17:30 | Ovet | kyllä |
| 18:15 | Toimitusjohtajan puhe, 15 min | kyllä |
| 18:35 | Palkintojen jako, 40 min | kyllä |
| 19:30 | Bändi, 60 min | kyllä |
| 22:00 | Purku alkaa | kyllä |

### Muutosloki

| Pvm | Kuka | Mitä | Vaikutus | Tila |
| --- | --- | --- | --- | --- |
| 12.3. | Marja Lehtinen (tilaaja) | Puhe 18:00 → 18:15 | aikataulu +15 min | hyväksytty |
| 20.3. | Bändin tuotantopäällikkö (rider v2) | Langattomia mikrofoneja 2 → 4 | +180 | odottaa hyväksyntää |
| 20.3. | Bändin tuotantopäällikkö (rider v2) | Monitorilinjoja 4 → 6 | +240 | odottaa hyväksyntää |
| 20.3. | Bändin tuotantopäällikkö (rider v2) | Soundcheck 45 → 75 min | aikataulu +30 min | odottaa hyväksyntää |
| 2.4. | Marja Lehtinen (tilaaja) | Striimaus lisätään | +1 450 | eskaloitu, ylittää mandaattikaton |

Kolme 20.3. riviä syntyivät automaattisesti, kun bändin tuotantopäällikkö latasi
riderin version 2. Ne ovat saman latauksen tuottamia ja liittyvät toisiinsa.

### Päätöskohdat

**Lopullinen ohjelma.** Päättäjä Marja Lehtinen. Määräaika 11.4.
Jos päätöstä ei tule: versio 4 jää voimaan ja sen jälkeiset muutokset laskutetaan
erikseen. Tila: avoin, 3 päivää jäljellä.

**Esitysgrafiikat.** Omistaja Nordkraftin markkinointi. Määräaika 13.4.
Tila: 2 kolmesta saapunut, yksi myöhässä.

## Näkymä A: asiakas

### Sisältö

Yksi sivu, joka sisältää järjestyksessä:

1. Mitä minulta odotetaan juuri nyt
2. Päätöskohdat määräaikoineen ja oletuksineen
3. Aikataulu (vain asiakkaalle näkyvät rivit)
4. Muutosloki
5. Toimitettavat tiedostot ja niiden tila
6. Yhteystiedot

### Tärkein yksittäinen elementti

**Päätöskohta, jolla on oletus.** Se ei ole tehtävälistan rivi eikä ilmoitus.
Se on määräaika, jolla on seuraus: "jos et päätä 11.4. mennessä, versio 4 jää
voimaan ja myöhemmät muutokset laskutetaan erikseen".

Tämä on koko tuotteen omaperäisin käyttöliittymäelementti ja ansaitsee eniten
suunnitteluhuomiota. Sen pitää olla painava mutta ei uhkaava: se on sopimusehto,
ei muistutus.

### Muutoslokin ryhmittely

Loki ei ole aikajärjestyksessä oleva syöte. Se on ryhmitelty tilan mukaan, ja
**odottaa sinua** on ylimpänä. Vasta sen alla hyväksytyt ja hylätyt.

Ryhmittele saman latauksen tuottamat rivit yhteen ("Riderin päivitys 20.3.,
3 muutosta, yhteensä +420"), koska ne hyväksytään tai hylätään yhdessä.

Jokaisella rivillä näkyy pyytäjä, päivämäärä, kustannus- tai aikatauluvaikutus
ja tila. Eskaloidulla rivillä näkyy myös kenelle se meni ja miksi.

### Ilme

Rauhallinen ja luettava. Yksi sarake, väljä rytmi, iso luettava typografia,
vaalea pohja. Tämä on sivu jonka avaa ihminen, joka ei tunne tapahtumatekniikkaa
ja jolla on kiire.

**Ei navigaatiota.** Yksi linkki on yksi sivu. Ei sivupalkkia, ei välilehtiä,
ei murupolkua. Jos sisältöä on paljon, käytä ankkureita tai laskostuvia osioita,
älä reitityksiä.

Toimii puhelimella yhtä hyvin kuin työpöydällä. Tee molemmat.

## Näkymä B: tuottaja

### Sisältö

Sama tuotanto, mutta tekninen totuus:

1. Hyväksyntäjono: mikä odottaa ketä, ja mitkä ovat myöhässä
2. Koko aikataulu, myös asiakkaalta piilotetut rivit, riippuvuuksineen
3. Tarvelista kategorioittain (ääni, valo, video, virta, rigi, henkilöstö)
4. Ehdotetut tarpeet erottuvat vahvistetuista, ja jokaisella ehdotetulla näkyy
   **lähdelainaus**: se rivi riderista, josta se syntyi
5. Toimitettavien tila ja yhden klikkauksen muistutus myöhässä oleville

### Tärkein yksittäinen elementti

**Ehdotettu tarve lähteineen.** Riderin versiosta 2 parsittu rivi, jonka vieressä
näkyy alkuperäinen lause siitä dokumentista. Käyttäjä voi vahvistaa tai hylätä
näkemättä koko dokumenttia.

Tämä on se, minkä varassa koko tekoälyosuus seisoo: käyttäjän ei tarvitse luottaa,
hän voi tarkistaa sekunnissa. Suunnittele se niin että tarkistaminen on nopeampaa
kuin epäileminen.

### Ilme

Tiheä ja tiukka. Taulukkomainen, monta saraketta, pienempi typografia, enemmän
dataa per pikseli, näppäimistöystävällinen. Tummempi tai neutraalimpi pohja kuin
asiakasnäkymässä.

Tätä katsotaan monta kertaa päivässä ja usein kiireessä. Tiheys on ominaisuus,
ei laiminlyönti.

## Yhteiset säännöt

- **Sama sanasto molemmissa.** Jos asiakasnäkymä sanoo "muutos odottaa
  hyväksyntääsi", tuottajan näkymä ei sano "pending change request".
- **Suomi.** Kaikki käyttöliittymäteksti suomeksi, myös tuottajan näkymässä.
- **Yksi paikka, joten paikkatasoa ei näytetä.** Tässä tuotannossa on yksi lava.
  Repon periaate on "taso ilmestyy vasta kun sitä on kaksi", eli käyttöliittymässä
  ei saa näkyä lavavalitsinta, lavanavigaatiota eikä sanaa "lava" rakenteena.
- **Rahasummat ilman valuuttasymbolia tai symbolin kanssa, valitse toinen ja pidä
  se.** Summat ovat keksittyjä.
- Näytä molemmat näkymät niin, että ne voi asettaa rinnakkain samaan kuvaan.

## Mitä EI suunnitella

Nämä ovat tarkoituksellisia poisjättöjä, eivät unohduksia. Jos jokin näistä
ilmestyy mockupiin, se on merkki siitä että konsepti on ymmärretty väärin.

- **Ei kirjautumissivua.** Sidosryhmillä ei ole tilejä. Linkki on pääsy.
- **Ei chattia, kommenttiketjuja eikä yleistä keskustelua.** Keskustelu kiinnittyy
  aina yksittäiseen ehdotukseen.
- **Ei kansiopuuta eikä tiedostoselainta.** Tiedosto kiinnittyy objektiin.
- **Ei asetussivua, käyttäjähallintaa eikä roolimatriisia.**
- **Ei KPI-kortteja, mittaristoja, donitsikaavioita eikä dashboard-estetiikkaa.**
  Tilaajalla ei ole tässä mitään mitattavaa. Hänellä on päätöksiä ja määräaikoja.
- **Ei tekoälyassistenttia, chat-kuplaa eikä "kysy Downstagelta" -painiketta.**
  Malli toimii taustalla ehdotusten tuottajana, ei keskustelukumppanina.

## Toivotut ulostulot

- Interaktiivinen prototyyppi, jossa pääsee molempiin näkymiin
- Asiakasnäkymä työpöydälle (1440) ja puhelimelle (390)
- Tuottajan näkymä työpöydälle (1440)
- Itsenäinen HTML-vienti, joka voidaan tallentaa tähän kansioon
- Lyhyt perustelu siitä, miksi päätöskohta ja lähdelainaus on suunniteltu juuri
  näin, koska ne ovat ne kaksi elementtiä joista tässä on kyse
