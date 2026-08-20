# Prompti kierros 04: tuottajanäkymä mobile-first

Syöte Claude Designille. Liitä repo mukaan kontekstiksi.

---

## Lue ensin

1. `mockups/04-tuottaja-mobile/suunnitelma.md`. **Se on tämän kierroksen pohja**,
   ja siinä on diagnoosi, periaatteet ja purkulista.
2. `docs/konsepti.md`, `docs/tietomalli.md`, `docs/tiedostot.md`
3. Kierrosten 01, 02 ja 03 promptit ja muistiinpanot

## Vienti

Kierroksen 03 vienti oli oikein: yksi itsenäinen HTML-tiedosto, ei ulkoisia
viittauksia, ei erillistä tukitiedostoa. **Tee samoin.**

## Tämä kierros ei lisää mitään

Sanon tämän ensin, koska se on helpoin ohje unohtaa.

Tuottajan pintaa on nyt noin kymmenen erillistä näkymää kolmelta kierrokselta.
Ne eivät ole huonoja yksittäin, mutta niillä ei ole yhteistä selkärankaa, ja siksi
sama `muutos`-rivi näyttää neljältä eri asialta.

**Tämä kierros on pelkkää purkamista ja uudelleen kokoamista.** Jos jokin asia ei
esiinny jo kierroksissa 01, 02 tai 03, sitä ei suunnitella nyt. Ei uusia
toiminnallisuuksia, ei uusia näkymiä, ei parannuksia jotka tulivat mieleen matkalla.

Jos huomaat että jotain puuttuu, kirjoita se loppuun listaksi. Älä suunnittele sitä.

## Suunnittelujärjestys, ja se on osa ohjetta

**Kortti ensin, yksin, 390 pikselin leveydellä. Kaikki muu johdetaan siitä.**

Älä aloita kotinäkymästä. Jos aloitat ruudusta, päädyt sommittelemaan paneeleja,
ja se on täsmälleen se ongelma jota tässä korjataan.

## 1. Kortti

Yksi korttimalli, joka palvelee neljää eri tietotyyppiä:

- hinnoittelua odottava muutos
- parsimaton tai osittain parsittu lähdedokumentti
- myöhässä oleva toimitettava
- päätöskohta, jonka määräaika lähestyy

Näytä kaikki neljä vierekkäin **samanmuotoisina**. Se on tämän kierroksen tärkein
yksittäinen todiste: tuottajan näkökulmasta nämä ovat sama asia, työtä jolla on
määräaika, vaikka ne ovat tietomallissa eri tauluja.

Kortin runko:

```
otsikko    mitä
rivi 2     kuka ja milloin
rivi 3     vaikutus: raha, aika, tai kumpikin
lähde      lainaus tai viittaus, jos sellainen on
toiminnat  ensisijainen · toissijainen · hylkää
```

**Kortti on tiheä. Ruudulla on vähän kortteja.** Tiheys on korttikohtaista eikä
ruutukohtaista, ja siinä on koko ratkaisu siihen, miten ammattimainen tuntuma
säilyy ilman tietoseinää.

Kierroksen 03 triage-kortti on jo lähes tämä. Yleistä se, älä keksi uutta.

## 2. Jono

Kotinäkymä on **yksi järjestetty lista kaikesta, mikä odottaa tuottajaa**,
tyypistä riippumatta. Ei neljää paneelia.

**Järjestyssääntö:** ensin se, jonka laiminlyönnistä seuraa jotain aikaisimmin.
Käytännössä päätöskohdat, joiden oletus on laukeamassa, ennen kaikkea muuta.
Sitten se, mikä estää jotakuta toista etenemästä. Vasta sitten summa.

Tee tämä järjestys näkyväksi. Jono ei ole tehtävälista vaan seurausten järjestys,
ja käyttäjän pitää nähdä miksi ylin rivi on ylin.

Yläpuolella yksi rivi kontekstia: tuotanto, päivä, T-luku, tuotannon tila.
Alapuolella tämän päivän aikataulusiivu, tiivistettynä.

### Tyhjä jono on oma ruutunsa, ja se on tärkeä

Suunnittele se huolella. Se on ainoa kerta, kun tuote saa sanoa että kaikki on
kunnossa, ja tapahtumatuotannossa se hetki on harvinainen ja arvokas. Älä tee
siitä tyhjää tilaa, jossa lukee "ei kohteita".

## 3. Sama jono työpöydällä

Leveämpi, ei uutta rakennetta. Enemmän kortteja näkyvissä kerralla ja enemmän
sisältöä kortin sisällä, mutta sama järjestys ja samat toiminnot samassa
järjestyksessä.

**Työpöytä on leveämpi mobiili, ei mobiili pienempi työpöytä.**

## 4. Yksi katselmuspinta, rehellisesti työpöytäkohtaisena

Ota esimerkiksi koko tarvelista kategorioittain, tai kuormalista laskentoineen.

Näytä se leveänä ja tiheänä, niin kuin sen kuuluukin olla. Ja näytä sitten sama
näkymä 390 pikselissä niin, että se **kertoo suoraan olevansa parempi koneella** ja
antaa lukukelpoisen tiivistelmän sen sijaan että puristaisi kaksitoista saraketta
puhelimeen.

Tämä ruutu on tarkoituksellinen myönnytys. Se on tuotteessa rehellisempi ratkaisu
kuin teeskennellä että kaikki toimii kaikkialla.

## 5. Muokkaus tapahtuu kortin päällä

Kierroksen 03 näkymät A1, A2 ja A3 eivät ole kolme ruutua vaan yksi kortti, joka
käyttäytyy eri tavoin tuotannon tilan mukaan. Näytä se: sama kortti luonnostilassa
ja vahvistetussa tuotannossa.

A5, päätöskohdan luonti, jää omaksi lomakkeekseen, mutta se avautuu levynä kortin
päälle eikä omana sivunaan.

## 6. Käyttöympäristö

Tätä käytetään pimeässä hallissa, seisten, yhdellä kädellä, usein kiireessä.
Tuottajan näkymä pysyy tummana. Kosketuskohteet ovat riittävän isoja käytettäväksi
katsomatta tarkasti, ja toiminnot ovat ruudun alaosassa peukalon ulottuvilla.

## Mitä EI suunnitella

Kaikki aiempien kierrosten poisjätöt ovat voimassa: ei kirjautumista, ei chattia,
ei kansiopuuta, ei asetuksia tai roolimatriisia, ei KPI-kortteja tai kaavioita,
ei tekoälyassistenttia, ei lavatasoa, ei vaihepalkkia, ei "haluatko varmasti"
-dialogeja, ei versiohistorian selainta.

Tällä kierroksella lisäksi, ja nämä ovat juuri ne joita mobiilisuunnittelu tuo
mukanaan automaattisesti:

- **Ei alanavigaatiopalkkia.** Ei välilehtirivi ruudun alalaidassa. Navigaatiota on
  yksi taso: jono ja yksi kohde.
- **Ei ylänavigaatiota, ei sivupalkkia, ei hampurilaisvalikkoa.** Katselmuspinnat
  ovat linkkejä jonon alalaidassa.
- **Ei muokattavaa kotinäkymää eikä widgettejä.** Jono on järjestetty säännöllä,
  ei käyttäjän mieltymyksellä.
- **Ei animaatioita, jotka viivyttävät toimintaa.**
- **Ei uusia ominaisuuksia.** Katso kohta "tämä kierros ei lisää mitään".

## Peukalotesti

Viisi tavallisinta päivittäistä toimenpidettä pitää pystyä tekemään yhdellä
peukalolla, ilman että laitetta tarvitsee siirtää kädessä:

1. Hinnoittele muutos
2. Hyväksy tai hylkää
3. Kysy tarkennus
4. Muistuta myöhässä olevaa
5. Katso mitä seuraavaksi

Osoita jokainen näistä jossakin ruudussa.

## Toivotut ulostulot

- Neljä korttityyppiä vierekkäin, 390
- Jono, 390, sekä täytenä että tyhjänä
- Sama jono, 1440
- Yksi katselmuspinta, 1440 ja 390
- Kortti luonnostilassa ja vahvistetussa tuotannossa
- Yksi itsenäinen HTML-tiedosto
- Lyhyt perustelu kahdesta asiasta: miten järjestyssääntö tehtiin näkyväksi, ja
  mistä neljästä paneelista luovuttiin ja mihin niiden sisältö meni
- Loppuun lista siitä, mitä huomasit puuttuvan mutta et suunnitellut
