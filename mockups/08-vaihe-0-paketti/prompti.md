# Prompti kierros 08: vaihe 0 -paketti

Syöte Claude Designille. Liitä repo mukaan kontekstiksi.

---

## Lue ensin

1. `docs/mvp.md`, **erityisesti vaihe 0 ja mittarit**. Tämä kierros toteuttaa sen.
2. `mockups/06-asiakaspinta/` ja `mockups/07-kun-kukaan-ei-katso/`
3. `docs/konsepti.md` ja `docs/tietomalli.md`
4. Kierrosten 04, 05, 06 ja 07 muistiinpanot

## Vienti

Kuten aiemmin: yksi itsenäinen HTML-tiedosto. Tässä kierroksessa sillä on myös
toinen merkitys, koska osa tuotoksesta on tarkoitus oikeasti käyttää.

## Miksi tämä kierros on erilainen

Seitsemän kierrosta on suunnitellut tuotteen päästä päähän. Puuttuvien listat ovat
muuttuneet aukoista reunatapauksiksi, eli pinta on katettu.

`docs/mvp.md`:n vaihe 0 on silti tekemättä. Se sanoo näin:

> Ota kahdesta kolmeen omaa keikkaa. Ylläpidä jokaisesta yhtä jaettua sivua käsin.
> Tämä maksaa yhden viikonlopun ja vastaa kalleimpaan kysymykseen ennen kuin
> riviäkään sovelluskoodia on kirjoitettu. Jos asiakkaat eivät avaa linkkiä,
> konseptin ydin on väärä ja loput vaiheet ovat turhia.

**Kahdeksas suunnittelukierros ilman yhtäkään mittausta olisi täsmälleen se virhe,
jota vastaan mvp.md kirjoitettiin.**

Siksi tämä kierros ei suunnittele tuotetta. Se suunnittelee sen, millä tuote
testataan: paketin, jota yksi ihminen ylläpitää käsin oikealla keikalla ilman
mitään taustajärjestelmää.

## Suunnitteluongelma

**Mitä jää jäljelle, kun ohjelmisto poistetaan?**

Vaiheessa 0 ei ole tietokantaa, ei kirjautumista, ei latauksia, ei parsintaa, ei
jonoa, ei automaattisia viestejä. Tuottaja kirjoittaa sivun käsin ja lähettää
viestit itse.

Jäljelle jäävän pitää silti testata hypoteesi:

> Kun asiakas näkee saman totuuden kuin tuottaja, ja jokainen pyyntö kirjautuu
> kustannusvaikutuksineen samaan lokiin, sähköpostien määrä ja jälkikäteiset
> erimielisyydet vähenevät mitattavasti.

Ja sen alla oleva riskialttiimpi oletus: **asiakas avaa linkin ilman että häntä
pitää opettaa.**

### Toinen, yhtä kova reunaehto

**Yhden päivityksen pitää onnistua alle kymmenessä minuutissa.**

Jos ylläpito vie enemmän, tuottaja ei jaksa kolmea viikkoa, ja testi epäonnistuu
väärästä syystä: emme saa tietää oliko konsepti oikea, vaan sen että ylläpito oli
työlästä.

Suunnittele siis myös se, miten sivua ylläpidetään, ei vain miltä se näyttää.

## A. Sivu

Yksi staattinen sivu, jonka tuottaja täyttää käsin oikealle keikalle.

Kolme osaa, ja tasan kolme, koska `docs/mvp.md` vaihe 0 nimeää ne:

1. **Aikataulu**
2. **Muutosloki**, jossa päivämäärä, kuka pyysi, ja mitä se maksoi
3. **Päätöskohdat**: mitä pitää päättää, kuka päättää, mihin mennessä, ja mitä
   tapahtuu jos päätöstä ei tule

Kierrokset 01 ja 06 ovat suunnitelleet nämä. Käytä niitä, älä keksi uutta.
**Karsi kaikki, mikä vaatii ohjelmistoa:** ei tiedostojen validointia, ei
lataamista, ei ehdotusnappia, ei tilamuutoksia, ei laskentaa.

Jos jokin kierrosten 01 ja 06 elementti ei toimi ilman taustajärjestelmää, poista
se ja kerro listassa mitä poistit. Se lista on arvokasta tietoa: se kertoo, mikä
osa tuotteesta on ohjelmistoa ja mikä osa on pelkkä sopimus muodosta.

## B. Ylläpito

Sivun lähdemuoto, jota tuottaja muokkaa. Ehdota konkreettinen tapa ja perustele se
kymmenen minuutin rajaa vasten.

Näytä, miltä yksi tavallinen päivitys näyttää alusta loppuun: asiakas lähetti
sähköpostissa muutospyynnön, ja tuottaja vie sen sivulle.

Ota kantaa myös siihen, mikä on riittävä hosting tälle. Se ei ole suunnittelukysymys
mutta se on este, jos sitä ei ratkaista.

## C. Viestit, jotka lähetetään käsin

Kierros 07 suunnitteli neljä automaattista viestityyppiä ja laski, että tilaaja saa
yhdeksän viestiä tuotannon aikana.

Vaiheessa 0 tuottaja lähettää ne itse. Tee niistä **valmiit mallipohjat**, joihin
täytetään nimet ja päivämäärät:

1. Linkki saapuu ensimmäisen kerran (kierros 06 ruutu A on tämän pohja)
2. Määräaika lähestyy
3. Oletus laukesi

Säilytä kierroksen 07 sävysäännöt sellaisenaan. Erityisesti se testi: voiko
tuottaja lähettää tämän ihmiselle, jonka kanssa hän tekee töitä myös ensi vuonna.

## D. Mittauslomake

`docs/mvp.md` nimeää viisi mittaria ja sanoo, että vertailukohta pitää kerätä
**ennen** kuin mitään muuttuu.

Suunnittele yksi sivu, jolle ne kirjataan:

- Avasiko asiakas linkin, ja montako kertaa
- Sähköpostien määrä per tuotanto
- Jälkikäteisten erimielisyyksien määrä
- Tunteja tarjouksen tekemiseen
- Toimitettavia määräaikaan mennessä, prosentteina

Kaksi saraketta: **vertailukeikka** ilman Downstagea ja **testikeikka** sen kanssa.

Ratkaise myös se, miten ensimmäinen mittari mitataan ilman analytiikkaa, koska
staattisella sivulla ei ole kävijäseurantaa eikä sitä pidä tähän rakentaa.
Jos ainoa rehellinen vastaus on kysyä asiakkaalta jälkikäteen, sano se.

## Mitä EI suunnitella

Kaikki aiempien kierrosten poisjätöt ovat voimassa.

Tällä kierroksella lisäksi:

- **Ei mitään, mikä vaatii taustajärjestelmän.** Tämä on koko kierroksen idea.
- **Ei kävijäseurantaa, evästeitä eikä analytiikkaskriptejä.** Sivu menee oikealle
  asiakkaalle oikeassa tuotannossa.
- **Ei tuotteen nimeä isolla eikä mainintaa siitä, että tämä on koe.** Asiakkaan
  näkökulmasta tämä on hänen tapahtumansa sivu, ei pilotti johon hän osallistuu.
- **Ei paikkoja, jotka jäävät tyhjiksi.** Jos jotain ei voi ylläpitää käsin, sitä
  ei ole sivulla lainkaan. Tyhjä osio on pahempi kuin puuttuva osio.

## Toivotut ulostulot

- Sivu täytettynä uskottavalla keksityllä keikalla, 390 ja 1440
- Sama sivu tyhjänä pohjana, eli se mistä tuottaja aloittaa
- Yhden päivityksen kulku alusta loppuun
- Kolme viestimallipohjaa
- Mittauslomake, kaksi saraketta
- Yksi itsenäinen HTML-tiedosto
- Lyhyt perustelu kahdesta asiasta: mikä karsiutui pois kun ohjelmisto poistettiin,
  ja miten kymmenen minuutin raja saavutetaan
- Loppuun lista siitä, mitä huomasit puuttuvan mutta et suunnitellut
