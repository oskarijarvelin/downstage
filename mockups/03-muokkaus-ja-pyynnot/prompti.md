# Prompti kierros 03: muokkaustyökalut ja muutospyynnöt

Syöte Claude Designille. Liitä repo mukaan kontekstiksi.

---

## Lue ensin

1. `docs/konsepti.md`, `docs/tietomalli.md`, `docs/tiedostot.md`.
   **Dokumentteja on päivitetty kierroksen 02 jälkeen.** Uutta ovat kentät
   `muutos.kustannusarvio`, `slot.nakyy_asiakkaalle` ja dokumentin tila
   `osittain_parsittu`.
2. `mockups/01-asiakas-ja-tuottaja/` ja `mockups/02-muutoksen-elinkaari/`,
   molempien `prompti.md` ja `muistiinpanot.md`.

Kierrokset 01 ja 02 onnistuivat. Peri niiden ilme, sanasto ja rakenne sellaisenaan.
Jos alla oleva on ristiriidassa dokumenttien kanssa, dokumentit voittavat.

## Vientivaatimus, korjattu

Kierroksen 02 vaatimus itsenäisestä HTML:stä oli mahdoton, koska vientimuoto lataa
Reactin ja Babelin verkosta. Se oli väärin kirjoitettu ohje, ei väärin noudatettu.

Nyt: **vie `support.js` samaan kansioon HTML-tiedostojen kanssa.** Kummassakaan
aiemmassa kierroksessa sitä ei tullut mukana, ja siksi mitään ei pystynyt katsomaan
sellaisenaan. Kerro erikseen, mitkä tiedostot kuuluvat yhteen.

## Mitä tällä kierroksella suunnitellaan

Kaksi puuttuvaa puoliskoa. Tähän asti on mockattu vain lukemista ja hyväksymistä:
kukaan ei ole voinut luoda eikä muuttaa mitään.

**A. Tuottajan muokkaustyökalut.**
**B. Asiakkaan tapa lähettää uusi muutospyyntö.**

Sama keksitty tuotanto kuin aiemmin (Kevätgaala 2027, Nordkraft Oy, 14.4.2027).
Kaikki nimet ja summat ovat kuvitteellisia.

## Koko kierroksen vaikein asia

> **Sama muokkaus käyttäytyy eri tavoin ennen ja jälkeen tuotannon vahvistusta.**

Ennen vahvistusta tuottaja muuttaa kentän, ja se vain muuttuu. Vahvistuksen jälkeen
sama muutos samassa kentässä synnyttää muutosrivin, jolla on kustannusvaikutus ja
joka menee tilaajalle. Tämä on `docs/tietomalli.md`:n sääntö 2.

**Tilaa ei valita kytkimestä. Tuotannon tila ratkaisee sen.** Käyttäjä ei siis
koskaan päätä, haluaako hän tehdä "ison" vai "pienen" muokkauksen.

Suunnittele tälle oma vertailunäkymä: sama kenttä, sama käyttäjä, sama arvo,
kaksi eri seurausta vierekkäin. Se on tämän kierroksen tärkein ruutu.

## A. Tuottajan muokkaustyökalut

**A1. Luonnostila, vapaa muokkaus.** Aikatauluun lisätään slot, muokataan kestoa,
poistetaan rivi. Tarvelistalle lisätään rivejä. Ei muutoslokia, ei hintalappuja,
ei vahvistusaskelia. Näytä miltä muokkaaminen näyttää silloin kun se on halpaa.

**A2. Vahvistettu tila, sama muokkaus.** Tuottaja pidentää soundcheckin kestoa.
Ruudulle ilmestyy, että tästä syntyy muutosrivi, ja hänen on annettava sille
kustannusvaikutus ennen kuin se lähtee tilaajalle.

Olennaista: **muutosrivi itse on se vahvistus.** Älä lisää erillistä
"haluatko varmasti" -dialogia sen päälle.

**A3. Poisto vahvistuksen jälkeen.** Slot poistetaan ohjelmasta. Sekin on muutos,
ja sen kustannusvaikutus voi olla negatiivinen. Näytä hyvitys, koska se on
tapahtumatuotannossa yhtä tavallinen kuin lisäys, ja koska se on hyvä testi sille,
ettei muutosloki oleta muutosten kasvattavan laskua.

**A4. Osapuolen lisääminen ja linkin jakaminen.** "Jaa tämä" siitä näkymästä jossa
olet, ei erillinen käyttäjähallinta. Näytä mitä jaettaessa valitaan: mikä objekti,
mikä näkymä (`asiakas`, `logistiikka`, `tekninen`) ja milloin linkki vanhenee.
Näytä myös esikatselu siitä, mitä vastaanottaja tulee näkemään.

**A5. Päätöskohdan luonti.** Nimi, päättäjä, määräaika ja oletus.

**Oletus on pakollinen kenttä, ei valinnainen.** Päätöskohtaa ei voi tallentaa
ilman vastausta kysymykseen "mitä tapahtuu jos kukaan ei päätä". Suunnittele
lomake niin, että tämä pakko tuntuu perustellulta eikä kiusalliselta.

## B. Asiakkaan muutospyyntö

**B1. Pyyntö kiinnittyy aina objektiin.** Se lähtee aikataulurivistä, tarpeesta tai
tiedostopaikasta, ei erillisestä lomakkeesta sivun laidassa. Kelluva
"lähetä pyyntö" -painike tekisi tästä yhteydenottolomakkeen.

**B2. Lomake on rakenteinen.** Mihin kohdistuu (esitäytetty), mitä halutaan,
milloin tarvitaan vastaus. Vapaa teksti on yksi kenttä muiden joukossa, ei koko
lomake.

**B3. Lähetetyllä pyynnöllä ei ole hintaa.** Tilaaja voi halutessaan antaa oman
arvion, mutta se menee kenttään `kustannusarvio` eikä sido mitään.

Näytä tämä symmetria eksplisiittisesti: **ihmisen kirjoittama pyyntö ja mallin
riderista parsima rivi päätyvät samaan tilaan, `odottaa hinnoittelua`.** Alkuperä
näkyy rivillä, mutta se ei muuta käsittelyä. Tämä on koko konseptin kannalta iso
asia ja sen pitää näkyä ruudulla.

**B4. Kuittaus kertoo mitä tapahtuu seuraavaksi ja milloin.** Ei "kiitos
yhteydenotostasi", vaan konkreettinen seuraava askel ja se, että vastaus tulee
tähän samaan näkymään.

**B5. Tuottajan triage.** Sama pyyntö saapuu hyväksyntäjonoon. Kolme toimintoa:
hinnoittele, kysy tarkennus, hylkää perusteluineen. Hylkäys ilman perustelua ei ole
mahdollinen.

**B6. Tarkennuskysymys on tämän tuotteen ainoa sallittu keskustelu.** Suunnittele se
tiukasti rajattuna: kysymys ja vastaus kiinnittyvät tähän yhteen ehdotukseen, ja
kun ehdotus on päätetty, ketju sulkeutuu sen mukana. Ei kanavaa, ei yleistä ketjua,
ei mahdollisuutta aloittaa keskustelua ilman ehdotusta.

Tämä on kierroksen herkin kohta. Jos se lipsahtaa chatiksi, tuote on menettänyt
rakenteensa, ja `docs/konsepti.md` kieltää sen erikseen.

## Mitä EI suunnitella

Samat kahdeksan poisjättöä kuin aiemmin, ja ne ovat pitäneet molemmilla
kierroksilla. Lisäksi tällä kierroksella:

- **Ei "tallenna"-painiketta, joka tallentaa koko sivun.** Muokkaus kohdistuu
  riviin, ei lomakkeeseen.
- **Ei "haluatko varmasti" -dialogeja.** Vahvistetussa tuotannossa muutosrivi on
  se vahvistus, ja luonnostilassa vahvistusta ei tarvita.
- **Ei versiohistorian selainta.** Kysymys on aina "mikä oli voimassa silloin", ja
  siihen vastaa muutosloki.
- **Ei yleistä kommentointia.** Katso B6.

## Toivotut ulostulot

- Vertailunäkymä: sama muokkaus ennen ja jälkeen vahvistuksen
- Viisi tuottajan näkymää (A1 - A5)
- Kuusi asiakkaan ja tuottajan näkymää (B1 - B6), asiakaspuoli myös leveydellä 390
- `support.js` samassa kansiossa
- Lyhyt perustelu kahdesta asiasta: miten luonnostilan ja vahvistetun tilan ero
  tehtiin näkyväksi ilman tilakytkintä, ja miten tarkennuskysymys rajattiin niin
  ettei siitä tule chattia
