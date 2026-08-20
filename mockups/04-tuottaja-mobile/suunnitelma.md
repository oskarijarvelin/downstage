# Tuottajanäkymän selkeytys ja siirto mobile-firstiin

Suunnitelma ennen kierrosta 04. Perustuu kierrosten 01, 02 ja 03 mockupeihin
sellaisina kuin ne ovat repossa.

## 1. Diagnoosi

Tuottajan pintaa on nyt noin kymmenen erillistä näkymää: kierroksen 01 nelipaneelinen
kotinäkymä, kierroksen 02 parsinta, parsimatta ja seuraukset, sekä kierroksen 03
viisi muokkausnäkymää ja triage.

Ne eivät ole huonoja yksittäin. Ongelma on, että jokainen niistä suunniteltiin
vastauksena promptiin, ei paikkana tuotteessa. Siitä seuraa kolme konkreettista
oiretta.

**Sama objekti näyttää neljältä eri asialta.** Yksi `muutos`-rivi esiintyy
hyväksyntäjonon rivinä, diff-taulukon rivinä, seurausnäkymän rivinä ja triagen
korttina. Neljä visuaalista kieltä samalle asialle.

**Mikään paneeli ei ole vastaus kysymykseen "mitä nyt".** Neljä paneelia kilpailee
ruudun yläreunasta, koska yhtäkään ei ole nimetty ensisijaiseksi.

**Toiminnot ovat eri paikoissa eri näkymissä.** Vasta kierroksen 03 triage vakiinnutti
kolmikon hinnoittele, kysy tarkennus, hylkää.

### Juurisyy

Asiakasnäkymällä on selkäranka: "mitä sinulta odotetaan nyt" ylimpänä, yksi sivu,
ei navigaatiota. **Tuottajan näkymä ei koskaan saanut vastinetta sille.**

Se on järjestetty entiteettien mukaan, eli tietokannan mukaan: hyväksyntäjono,
aikataulu, tarvelista, toimitettavat. Tuottajan päässä ei kuitenkaan ole
entiteettejä vaan kysymyksiä, ja niistä yksi on ylitse muiden.

## 2. Miksi mobile-first on oikea korjaus

Määrittelin kierroksella 01 tuottajan näkymän työpöytäkohtaiseksi ja tiheäksi.
Perustelu oli tuotantotoimisto. Se oli väärä perustelu kahdesta syystä.

**Tuottaja ei istu.** Hän seisoo hallissa, kävelee, on pakettiautossa. Työpöytä on
poikkeus, ei sääntö.

**Ja tärkeämpi syy: mobile-first ei ole laitevalinta vaan kuri.** 390 pikselin
levyiselle ruudulle ei mahdu neljää paneelia, joten se pakottaa tekemään sen
priorisoinnin, joka nyt puuttuu. Sama työ työpöydällä voi jäädä tekemättä, koska
tilaa on ja kaiken voi näyttää.

### Mutta tiheys oli aito hyve, eikä sitä saa hukata

Tarvelista, kuormalista, patch ja laskenta ovat aidosti taulukkomaisia ja aidosti
parempia leveinä. Siksi pinta jaetaan kahtia:

| | Toimintapinta | Katselmuspinta |
| --- | --- | --- |
| Mitä | Triage, hyväksyntä, hinnoittelu, yhden asian muokkaus, mitä seuraavaksi | Koko tarvelista, kuormalista, laskenta, aikataulu riippuvuuksineen |
| Milloin | Monta kertaa päivässä | Kerran tai kaksi per tuotanto, istuen |
| Suunta | **Mobile-first**, laajenee työpöydälle | **Leveä**, ja mobiilissa rehellisesti tiivistelmä |

**Sääntö: mobiili ei ole pienempi työpöytä, vaan työpöytä on leveämpi mobiili.**

Katselmuspinnan osalta on rehellisempää sanoa mobiilissa suoraan, että tämä
kannattaa avata koneella, ja näyttää siitä lukukelpoinen tiivistelmä, kuin puristaa
kaksitoista saraketta puhelimeen.

## 3. Kolme rakenteellista muutosta

### 3.1 Yksi jono, ei neljää paneelia

Tuottajan kotinäkymä on **yksi järjestetty lista kaikesta, mikä odottaa häntä**,
tyypistä riippumatta:

- hinnoittelua odottavat muutokset
- parsimattomat tai osittain parsitut lähdedokumentit
- myöhässä olevat toimitettavat
- päätöskohdat, joiden määräaika lähestyy

Nämä ovat tuottajan näkökulmasta sama asia: työtä, jolla on määräaika. Se, että ne
ovat tietomallissa eri tauluja, on toteutusyksityiskohta eikä syy neljälle
paneelille.

**Järjestyssääntö:** ensin se, jonka laiminlyönnistä seuraa jotain aikaisimmin.
Käytännössä päätöskohdat, joiden oletus on laukeamassa, ennen kaikkea muuta. Sen
jälkeen se, mikä estää jotakuta toista etenemästä. Vasta sitten summa.

Tämä sitoo jonon suoraan päätöskohdan oletukseen, joka on tuotteen omaperäisin
käsite. Jono ei ole tehtävälista vaan seurausten järjestys.

### 3.2 Yksi korttimalli kaikelle

Muutos, parsimaton tiedosto, myöhässä oleva toimitettava ja lähestyvä päätöskohta
renderöityvät **samanmuotoisena korttina**:

```
otsikko: mitä
rivi 2:  kuka ja milloin
rivi 3:  vaikutus (raha, aika, tai kumpikin)
lähde:   lainaus tai viittaus, jos sellainen on
toiminta: ensisijainen · toissijainen · hylkää
```

Kortti on tiheä. Ruudulla on vähän kortteja. **Tiheys on korttikohtaista, ei
ruutukohtaista**, ja siinä on koko ratkaisu ammattimaisen tuntuman säilyttämiseen
ilman seinää.

Kierroksen 03 triage on jo lähes tämä. Se yleistetään kaikkeen muuhun.

### 3.3 Toiminnot samassa paikassa, aina

Kolme toimintoa, samassa järjestyksessä, kortin alalaidassa, peukalon ulottuvilla:
ensisijainen, toissijainen, hylkää. Hylkäys vaatii aina perustelun.

Muokkaus tapahtuu kohteen päällä, ei omalla näytöllään. Kierroksen 03 näkymät
A1, A2 ja A3 eivät siis ole kolme ruutua vaan yksi kortti, joka käyttäytyy eri
tavoin tuotannon tilan mukaan. Vain A5, päätöskohdan luonti, jää omaksi lomakkeeksi,
ja sekin avautuu levynä kortin päälle.

## 4. Navigaatio

Yksi taso, kuten asiakasnäkymässä: **jono ja yksi kohde.** Kohteesta palataan jonoon.

Katselmuspinnat ovat linkkejä jonon alalaidassa, eivät välilehtiä yläreunassa.
Jos ylänavigaatiota alkaa tarvita, se on merkki siitä että jono ei tee työtään.

## 5. Mitä puretaan

| Nykyinen | Mihin menee |
| --- | --- |
| Kierroksen 01 neljä paneelia | Yksi jono plus tämän päivän aikataulusiivu |
| Muutoksen neljä visuaalista käsittelyä | Yksi kortti |
| A1, A2, A3 erillisinä näkyminä | Yksi kortti, joka käyttäytyy tuotannon tilan mukaan |
| Vaihe 5:n kaksisarakkeinen ennen ja jälkeen | Toimenpiteen jälkeinen "mikä muuttui" -kuittaus |
| Kierroksen 02 diff-taulukko | Kortti, jonka sisällä diff. Leveä versio katselmuspinnalla |

## 6. Vaiheistus

1. **Inventaario.** Listaa jokainen olemassa oleva tuottajan ruutu ja merkitse
   kumpaan luokkaan se kuuluu, toimintaan vai katselmukseen. Osa katoaa tässä.
2. **Kortti.** Suunnittele korttimalli ensin, yksin, 390 pikselin leveydellä.
   Kaikki muu seuraa siitä.
3. **Jono.** Järjestyssääntö ja tyhjä tila. Tyhjä jono on tärkeä ruutu: se on ainoa
   kerta kun tuote saa sanoa että kaikki on kunnossa.
4. **Laajennus työpöydälle.** Sama jono leveämpänä, ei uutta rakennetta.
5. **Katselmuspinnat erikseen** ja avoimesti työpöytäkohtaisina.

## 7. Onnistumisen mittari

Tuottajanäkymä on selkeä silloin kun molemmat pätevät:

- Kysymykseen "mitä minun pitää tehdä nyt" saa vastauksen alle kolmessa sekunnissa
  puhelimen ruudulta, ilman vierittämistä
- Muutos näyttää samalta joka paikassa, jossa se esiintyy

Kolmas, kova testi kierrokselle 04: **viisi tavallisinta päivittäistä toimenpidettä
pitää pystyä tekemään yhdellä peukalolla.** Ne ovat hinnoittele muutos, hyväksy tai
hylkää, kysy tarkennus, muistuta myöhässä olevaa, ja katso mitä seuraavaksi.

## 8. Mitä kierroksen 04 prompti pyytää

Ensin kortti yksin. Sitten jono. Sitten sama jono työpöydällä. Sitten yksi
katselmuspinta esimerkkinä siitä, miltä rehellisesti työpöytäkohtainen näkymä
näyttää puhelimessa.

Ei uusia toiminnallisuuksia. Tämä kierros on pelkkää purkamista ja uudelleen
kokoamista, ja se kannattaa sanoa promptissa ääneen, koska muuten mukaan tulee
ominaisuuksia.
