# Prompti kierros 05: jonon konteksti

Syöte Claude Designille. Liitä repo mukaan kontekstiksi.

---

## Lue ensin

1. `mockups/04-tuottaja-mobile/suunnitelma.md`, `prompti.md` ja `muistiinpanot.md`.
   **Kierros 04 onnistui.** Kortti, jono, kolme ryhmää ja seurausleima peritään
   sellaisenaan. Tämä kierros ei suunnittele niitä uudestaan.
2. `docs/konsepti.md`, erityisesti kohdat 3.3, 4.7 ja 6
3. `docs/tietomalli.md`, säännöt 2 ja 5
4. Kierrosten 01, 02 ja 03 muistiinpanot

## Vienti

Kuten kierroksella 04: yksi itsenäinen HTML-tiedosto, ei ulkoisia viittauksia.

## Mitä tällä kierroksella ratkaistaan

Kierroksen 04 jono tekee kaksi oletusta, ja molemmat ovat vääriä:

1. **Tuotantoja on yksi.** Käytännössä niitä on kesällä useita päällekkäin.
2. **Määräajat ovat päiviä.** Tapahtumapäivänä ne ovat tunteja ja minuutteja.

Nämä ovat sama kysymys: **mikä on jonon konteksti.** Siksi ne suunnitellaan yhdessä.

## Periaate, joka ratkaisee molemmat

> **Käyttäjä ei valitse kontekstia. Tila ratkaisee sen.**

Tämä on sama mekanismi, joka kierroksella 03 määritti muokkauksen käyttäytymisen:
luonnostilassa kenttä muuttuu, vahvistetussa siitä syntyy muutosrivi, eikä kytkintä
ole. Nyt sama laajenee jonoon.

Tuotannon tila ja kello ratkaisevat, miltä jono näyttää. Ei tilavalitsinta, ei
"tapahtumapäivätilaa", ei tuotantovalikkoa ylänavigaatiossa.

## A. Useampi rinnakkainen tuotanto

### A1. Yksi jono, ei montaa jonoa

Helppo ja väärä vastaus olisi tuotantovalitsin jonon yläpuolelle. Se lisäisi
navigaatiotason ja pakottaisi valitsemaan kontekstin ennen kuin näkee työtä.

Oikea vastaus tulee periaatteesta **"taso ilmestyy vasta kun sitä on kaksi"**
(`docs/konsepti.md` 3.3), mutta se ilmestyy kortille eikä navigaatioon:

- **Jono pysyy yhtenä.** Se on edelleen vastaus kysymykseen "mitä minun pitää tehdä
  nyt", eikä se kysymys välitä siitä, mihin tuotantoon asia kuuluu.
- **Tuotanto on kentän arvo kortilla**, ei jonon jakaja.
- **Järjestyssääntö on täsmälleen sama.** Päätöskohta, jonka oletus laukeaa
  huomenna keikalla A, on ylempänä kuin hinnoittelu keikalla B. Aina.

Ylärivin konteksti muuttuu yhden tuotannon rivistä usean tuotannon riviksi.
Suunnittele se niin, että siitä näkee kokonaiskuorman ilman että se on mittaristo.

Näytä myös se hetki, jossa toinen tuotanto lisätään: mikä ruudulla muuttuu, kun
tuotantoja on ensimmäistä kertaa kaksi.

### A2. Kohdistus on suodatin, ei navigaatiotaso

Kun tuottaja on paikan päällä yhdessä tuotannossa, muut ovat kohinaa.

**Kohdistus tapahtuu itsestään**, kun ollaan tuotannon tapahtumaikkunan sisällä.
Jono kertoo, että se on kohdistettu, ja kertoo mitä on piilossa ja kuinka paljon.
Ulospääsy on yhden kosketuksen päässä.

Tämä on suodatin, ei sivu. Suodatettu jono ei ole eri näkymä.

## B. Tapahtumapäivä

### B1. Ryhmittely vaihtuu, kun mittakaava vaihtuu

Kierroksen 04 kolme ryhmää (laukeaa itsestään, estää jotakuta toista, odottaa
päätöstä) on suunniteltu päivien mittakaavassa. Tapahtumapäivänä ne romahtavat
yhdeksi, koska kaikki on kiireellistä.

Silloin oikea akseli ei ole seurausluokka vaan **kello**: mitä nyt, mitä seuraavan
tunnin sisällä, mitä myöhemmin tänään.

Vaihdos tapahtuu itsestään. Näytä molemmat ryhmittelyt vierekkäin ja tee näkyväksi,
mikä sen vaihtoi.

### B2. Seurausleiman yksikkö vaihtuu

Kortin seurausleima on kierroksella 04 päiviä: "odottanut 19 pv", "oletus laukeaa
11.4.". Tapahtumapäivänä sama leima on minuutteja: "soundcheck alkaa 35 min".

Näytä sama kortti molemmilla asteikoilla vierekkäin. Se on pieni ruutu mutta se
kertoo koko kierroksen idean.

### B3. Tapahtumapäivän jono, pieni tuotanto

Rajaa tämä siihen, mitä `docs/konsepti.md` 4.7 jo kuvaa: mikä on seuraavaksi,
kuka on missä, yksi soittonappi, ja ongelmanappi joka ohjautuu oikealle ihmiselle.

**Älä lisää mitään sen yli.** Tapahtumapäivänäkymä on ollut listalla vaiheesta 5
asti, ja se houkuttelee keksimään ominaisuuksia.

### B4. Sama hetki isossa tuotannossa

`docs/konsepti.md` 4.7 sanoo, että isossa tuotannossa kysymys kääntyy: ei "mitä
seuraavaksi" vaan "mikä on rikki, missä, ja kuka on vapaana".

Näytä tämä kuudella lavalla. **Tämä on samalla ensimmäinen kerta, kun paikkataso
ilmestyy käyttöliittymään.** Kaikissa aiemmissa kierroksissa esimerkkituotannossa
on ollut yksi paikka, ja lavataso on ollut kielletty juuri siksi. Nyt sitä on
kaksi tai enemmän, joten sen kuuluu ilmestyä, ja tämä on ainoa ruutu jossa sen
saa näkyä.

Käytä keksittyä festivaalituotantoa, ei Kevätgaalaa. Kaikki nimet kuvitteellisia.

Jos kierros käy liian isoksi, tämä on se ruutu, jonka voi jättää pois. Kerro
silloin että jätit sen.

### B5. Offline

Jono on se näkymä, jonka pitäisi eniten toimia hallissa ilman verkkoa.

Näytä yksi ruutu: jono, jota ei ole synkronoitu hetkeen. Siitä pitää käydä ilmi
kaksi asiaa:

- **Milloin tämä tieto on peräisin.** Vanhentunut jono ei saa näyttää tuoreelta.
- **Mitkä toiminnot ovat turvallisia offline.** Merkintä tehdyksi on paikallinen ja
  voi odottaa. Hinnoittelu ja lähetys tilaajalle eivät ole, koska ne sitovat rahaa
  ja menevät toiselle osapuolelle.

Huomaa, että offline tehty toimenpide ei ole vielä muutoslokissa. Se on siis
ehdotus, joka ei ole vielä päässyt perille. Jos tämä paljastaa, että tietomalli
tarvitsee uuden tilan, sano se perusteluosassa.

## Mitä EI suunnitella

Kaikki aiempien kierrosten poisjätöt ovat voimassa: ei kirjautumista, ei chattia,
ei kansiopuuta, ei asetuksia tai roolimatriisia, ei KPI-kortteja tai kaavioita,
ei tekoälyassistenttia, ei vaihepalkkia, ei varmistusdialogeja, ei
versiohistorian selainta, ei alanavigaatiopalkkia, ei hampurilaisvalikkoa, ei
muokattavaa kotinäkymää.

Tällä kierroksella lisäksi:

- **Ei tuotantovalitsinta ylänavigaatiossa.** Katso A1 ja A2.
- **Ei tapahtumapäivätilan kytkintä.** Tila ratkaisee, ei käyttäjä.
- **Ei uusia ominaisuuksia tapahtumapäivään** sen yli, mitä konsepti 4.7 kuvaa.
- **Ei paikkatasoa muualla kuin ruudussa B4.**

## Toivotut ulostulot

- Jono usealle tuotannolle, 390
- Hetki, jossa toinen tuotanto lisätään
- Kohdistettu jono paikan päällä, 390
- Tapahtumapäivän jono, 390, sekä vertailu päiväryhmittelyyn
- Sama kortti päivä- ja tuntiasteikolla vierekkäin
- Tapahtumapäivä isossa tuotannossa, 390 ja 1440 (voi jättää pois, katso B4)
- Offline-jono, 390
- Yksi itsenäinen HTML-tiedosto
- Lyhyt perustelu kahdesta asiasta: miten kohdistus tehtiin ilman navigaatiotasoa,
  ja mikä vaihtaa ryhmittelyn tapahtumapäivänä
- Loppuun lista siitä, mitä huomasit puuttuvan mutta et suunnitellut
