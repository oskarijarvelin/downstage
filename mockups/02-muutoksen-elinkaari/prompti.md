# Prompti kierros 02: muutoksen elinkaari

Syöte Claude Designille. Liitä repo mukaan kontekstiksi.

---

## Lue ensin

1. `docs/konsepti.md`, `docs/tietomalli.md`, `docs/tiedostot.md`
2. `mockups/01-asiakas-ja-tuottaja/prompti.md` ja `muistiinpanot.md`

Kierros 01 onnistui. **Älä suunnittele sen ilmettä, sanastoa tai rakennetta
uudestaan.** Peri ne sellaisenaan ja jatka siitä. Jos jokin alla oleva on
ristiriidassa dokumenttien kanssa, dokumentit voittavat, ja kerro ristiriidasta.

## Kolme korjausta kierroksesta 01

**1. Itsenäinen HTML ilman ulkoisia riippuvuuksia.** Kaikki CSS, JS ja data samaan
tiedostoon. Kierroksen 01 vienti viittasi erilliseen `support.js`-tiedostoon, jota
ei ollut mukana, joten mikään ei renderöitynyt. Tämä ei saa toistua. Jokaisen
tiedoston pitää avautua selaimessa suoraan tiedostojärjestelmästä ilman palvelinta.

**2. Tilat omina ruutuinaan.** Kierroksella 01 päätöskohtakortissa näkyi
päällekkäin sekä päätöstä edeltävät painikkeet että kaksi päätöksen jälkeistä
tilaa, eikä pystynyt sanomaan oliko se tarkoitus. Näytä jokainen tila erillisenä
ruutuna, selkeästi otsikoituna.

**3. Säilytä kierroksen 01 keksintö.** Tuottajan aikatauluun oli lisätty sarake
sille, näkyykö rivi asiakkaalle. Sitä ei pyydetty, ja se on hyvä. Pidä se.

## Mitä tällä kierroksella suunnitellaan

**Yhden muutoksen koko elinkaari, alusta loppuun, kolmen eri osapuolen näkymissä.**

Tämä on konseptin terävin mekanismi ja vaikein selittää sanoin. Mockupin tehtävä
on tehdä siitä ymmärrettävä kuudessa ruudussa.

Käytä samaa keksittyä tuotantoa kuin kierroksella 01 (Kevätgaala 2027, Nordkraft Oy,
14.4.2027). Kaikki nimet ja summat ovat kuvitteellisia.

### Vaihe 1: lataus, vastapuolen näkymässä

Bändin tuotantopäällikkö avaa oman linkkinsä ja lataa riderin version 2.

**Tämä näkymä on uusi, eikä sitä ole mockattu aiemmin.** Tärkein kysymys, johon
sen pitää vastata: mitä vastapuoli näkee.

Ratkaisu tulee suoraan `docs/konsepti.md`:n kohdasta 7.1, "pääsy seuraa kohdetta,
ei ihmistä". Vastapuoli saa **saman asiakasrenderöinnin, rajattuna omaan
slottiinsa.** Ei siis neljättä käyttöliittymää, vaan sama sivu suppeampana.

Näytä eksplisiittisesti mikä katoaa: ei kokonaisbudjettia, ei muita esiintyjiä,
ei tuotannon muita päätöskohtia, ei tilaajan yhteystietoja. Jäljelle jää oma
soundcheck, oma input-lista, omat toimitettavat ja oma yhteyshenkilö tuotannossa.

### Vaihe 2: parsinta, tuottajan näkymässä

Rider v2 on purettu tietueiksi. Näytä diff versiota 1 vasten.

Kolme ehdotettua riviä, kukin **lähdelainauksineen**: se rivi riderista, josta
ehdotus syntyi. Muutokset ovat langattomat 2 → 4, monitorilinjat 4 → 6 ja
soundcheck 45 → 75 min.

**Uusi vaatimus, jota kierroksella 01 ei ollut.** Erota näkyvästi kaksi asiaa:

- **Mallin arvio** kustannuksesta, joka syntyi automaattisesti
- **Tuottajan hinnoittelema** summa, joka on lopullinen

Ehdotus ei saa näyttää valmiilta hinnalta ennen kuin ihminen on hinnoitellut sen.
Tämä on olennainen osa sitä, miksi mallille voi antaa tämän tehtävän: se ehdottaa,
ihminen sitoo.

### Vaihe 3: epäonnistunut parsinta

Samassa latauksessa tuli mukaan skannattu liite, jota malli ei osannut lukea.

Tila on `parsimatta`, ja tuottajalle on syntynyt tehtävä, jossa tiedosto on
liitteenä. Näytä tämä tila. Se on `docs/tiedostot.md`:n mukainen, eikä kierros 01
kata sitä lainkaan.

Olennaista: epäonnistuminen näkyy selvästi eikä hiljaa, eikä malli arvaa.
Käsin tehty parsinta on kelvollinen lopputulos.

### Vaihe 4: hyväksyntä, asiakasnäkymässä

Tilaajan yhteyshenkilö Marja Lehtinen näkee kolme muutosta yhtenä ryhmänä,
yhteensä +420, ja hyväksyy ne yhdellä toiminnolla. Summa on hänen
mandaattikattonsa 1 500 alapuolella.

Näytä myös rinnalla se tapaus, jossa summa ylittää katon: striimauslisäys +1 450
menee markkinointijohtajalle, ja Marjan ruudulla lukee ettei hänen tarvitse tehdä
sille mitään. Kierros 01 hoiti tämän hyvin, joten peri se ratkaisu.

### Vaihe 5: seuraukset

Hyväksyntä ei ole vain lokirivin tilamuutos. Näytä mitä se muuttaa:

- Soundcheck 15:00 venyy 30 minuuttia, ja aikataulu siirtyy sen mukana
- Tarvelistalle tulee kaksi langatonta ja kaksi monitorilinjaa lisää
- Muutosloki näyttää rivin lopullisena, päättäjineen ja aikaleimoineen

Näytä sama seuraus sekä asiakkaan että tuottajan näkymässä, jotta kahden
renderöinnin periaate näkyy myös muutoshetkellä.

### Vaihe 6: lasku

Tapahtuman jälkeen laskurivi, joka **johtuu suoraan muutoslokista.**

Jokaisella rivillä näkyy mistä muutoksesta se tulee, kuka sen pyysi ja kuka
hyväksyi. Tämän ruudun tehtävä on tehdä näkyväksi väite, että lasku kirjoittaa
itsensä lokista eikä sitä tarvitse perustella jälkikäteen.

## Yhteiset säännöt

- Sama sanasto ja sama ilme kuin kierroksella 01. Asiakas- ja vastapuolinäkymä
  rauhallisia ja vaaleita, tuottajan näkymä tiheä ja tumma.
- Kaikki käyttöliittymäteksti suomeksi.
- Yhä yksi paikka, joten lavatasoa ei näytetä missään.
- Jokainen vaihe omana ruutunaan, ja lisäksi yksi koontinäkymä, jossa koko
  elinkaari näkyy kerralla vasemmalta oikealle.

## Mitä EI suunnitella

Samat poisjätöt kuin kierroksella 01, ja ne pitivät silloin kaikki:

- Ei kirjautumissivua
- Ei chattia, kommenttiketjuja eikä yleistä keskustelua
- Ei kansiopuuta eikä tiedostoselainta
- Ei asetuksia, käyttäjähallintaa eikä roolimatriisia
- Ei KPI-kortteja, mittaristoja eikä kaavioita
- Ei tekoälyassistenttia eikä chat-kuplaa
- Ei lavatasoa eikä sanaa "lava" rakenteena

Lisäksi tällä kierroksella:

- **Ei edistymispalkkia tai vaihekaaviota käyttöliittymässä.** Elinkaari on tapa
  esittää mockup, ei komponentti tuotteessa. Käyttäjä ei koskaan näe "vaihe 3/6".

## Toivotut ulostulot

- Itsenäinen HTML, kaikki upotettuna, yksi tiedosto per näkymä
- Kuusi vaiheruutua plus koontinäkymä
- Vastapuolen näkymä sekä työpöydälle (1440) että puhelimelle (390)
- Lyhyt perustelu kahdesta asiasta: miten mallin arvio ja tuottajan hinnoittelu
  erotettiin toisistaan, ja mitä vastapuolen näkymästä jätettiin pois ja miksi
