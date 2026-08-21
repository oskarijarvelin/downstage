# Prompti kierros 07: Downstage silloin kun kukaan ei katso

Syöte Claude Designille. Liitä repo mukaan kontekstiksi.

---

## Lue ensin

1. `mockups/06-asiakaspinta/` kokonaisuudessaan, erityisesti ruutu A ja sen
   sähköpostin runko. **Tämä kierros jatkaa siitä.**
2. `docs/konsepti.md`, erityisesti 4.5 ja 7.3
3. `docs/mvp.md`, vaiheet 1 ja 2
4. `docs/tietomalli.md`, `paatoskohta` ja `toimitettava`
5. Kierrosten 04, 05 ja 06 muistiinpanot

## Vienti

Kuten kierroksilla 04, 05 ja 06: yksi itsenäinen HTML-tiedosto.

## Lähtötilanne

Kuusi kierrosta on suunnitellut ruutuja, joita joku katsoo.

Tuotteen keskeisin lupaus tapahtuu kuitenkin käyntien välissä.
`docs/konsepti.md` 4.5 sanoo sen näin: **järjestelmä jahtaa asiakasta, ei tuottaja**,
ja kutsuu sitä osaksi joka oikeasti palauttaa tuottajalle tunteja viikossa.
`docs/mvp.md` vaihe 1 laskee automaattisen muistutuksen mukaan pienimpään
toteutettavaan versioon.

**Sitä mekanismia ei ole suunniteltu lainkaan.** Sitä ei ole olemassa muualla kuin
proosana. Kierroksen 06 ruutu A piirsi ensimmäisen sähköpostin, ja se on ainoa
viesti, joka tuotteesta on koskaan lähtenyt ulos.

Tämä kierros suunnittelee sen, mitä Downstage tekee silloin kun kukaan ei katso.

## Kolme periaatetta

**1. Viesti on kutsu sivulle, ei sivun kopio.**
Jos viesti sisältää kaiken, ihmiset lakkaavat avaamasta linkkiä, ja koko yhden
linkin idea kuolee. Viestissä on tasan se, mitä tarvitaan päätökseen tulla
sivulle.

**2. Jokainen viesti kertoo seurauksen, ei muistuta.**
Sama logiikka kuin jonossa. Syy toimia ei ole se, että joku pyytää, vaan se mitä
tapahtuu jos ei toimi. Tuotteessa on jo tätä varten valmis rakenne: päätöskohdan
oletus.

**3. Määrä on suunnitteluongelma, ei viestien summa.**
Yksittäinen hyvä viesti on helppo. Kaksikymmentä hyvää viestiä on roskapostia.

**Laske ja näytä, montako viestiä yksi tilaaja saa yhden tuotannon aikana**, ja
perustele luku. Jos se on mielestäsi liian iso, karsi ja kerro mitä karsit. Tämä
on kierroksen tärkein yksittäinen vaatimus.

## Suunniteltavat viestit

Käytä samaa keksittyä tuotantoa kuin aiemmin (Kevätgaala 2027, Nordkraft Oy).
Kaikki nimet ja summat ovat kuvitteellisia. Kanava on tässä kierroksessa
**sähköposti**. Tekstiviestit ja push-ilmoitukset on rajattu tarkoituksella pois.

### 1. Määräaika lähestyy

Kolme tapausta eri etäisyyksillä ja eri vastaanottajille: rider T-14
vastapuolelle, lopullinen ohjelma T-3 tilaajalle, esitysgrafiikat T-1
markkinoinnille.

Sävy on tässä koko juttu. Viesti karhuaa sellaisen tuottajan puolesta, joka joutuu
tekemään näiden ihmisten kanssa töitä ensi vuonnakin.

### 2. Eskalointi

Mandaattikatto ylittyi, ja viesti menee henkilölle, joka ei todennäköisesti ole
koskaan avannut linkkiä.

Tämä on yhtä aikaa ensikontakti ja kiireellinen asia, ja se yhdistelmä on vaikea.
Vastaanottaja ei tiedä mikä Downstage on, mutta hänen pitää päättää tänään.

### 3. Oletus laukesi

**Tuotteen kaikkein vaikein viesti.** Kukaan ei päättänyt, määräaika meni, ja
sopimusehto astui voimaan: ohjelman versio 4 jäi voimaan ja myöhemmät muutokset
laskutetaan erikseen.

Viesti kertoo ihmiselle, että hänen tekemättä jättämisensä aiheutti seurauksen.
Se ei saa olla syyttävä eikä anteeksipyytelevä, ja sen pitää kertoa mitä nyt
voi tehdä.

Jos tämä viesti on väärässä sävyssä, koko oletusmekanismi muuttuu vihatuksi, ja
sen mukana menee tuotteen omaperäisin osa.

### 4. Mikä muuttui edellisen käynnin jälkeen

Tämä on pyydetty kolmella peräkkäisellä kierroksella (04, 05, 06) eikä sitä ole
suunniteltu. Nyt se suunnitellaan kahdessa muodossa:

- viestinä, joka lähtee kun jotain olennaista muuttui
- merkintänä sivulla, kun palaaja avaa linkin uudelleen

Ratkaise samalla se, mikä on olennaista. Kaikki muutokset eivät ansaitse viestiä,
ja `docs/tietomalli.md`:n muutosloki tietää kuka pyysi ja mitä se maksoi, joten
sääntö on johdettavissa datasta.

## Tuottajan puoli: mitä on lähdössä ja miten sen pysäyttää

Automaattinen karhuaminen on suhdebisneksessä vaarallista. Tuottaja on juuri
puhunut tilaajan kanssa puhelimessa, ja tunnin päästä järjestelmä lähettää samalle
ihmiselle muistutuksen samasta asiasta.

Suunnittele siis myös:

- **Mitä on lähdössä ja milloin.** Näkyvillä ennen kuin se lähtee.
- **Pysäytys.** Yksi kosketus, ja perustelu jää lokiin.
- **Mitä on lähtenyt.** Osa tuotannon historiaa, koska "eikö kukaan muistuttanut"
  on yhtä yleinen riita kuin "eikös sovittu".

Tämä sopii kierrosten 04 ja 05 jonoon. Selvitä, onko lähdössä oleva viesti oma
korttityyppinsä vai osa sitä korttia, jota se koskee. Perustele valinta.

## Loppu ja päättyminen

Kierroksen 06 puuttuvien listalla oli kolme tilaa, joita ei ole piirretty. Ne
kuuluvat tähän kierrokseen, koska nekin ovat sitä mitä tapahtuu ilman että kukaan
katsoo:

- **Tarjous hylättiin** tai tuotanto peruttiin. Mitä sivu sanoo.
- **Linkki vanheni.** Mitä sivulla lukee sen jälkeen, ja mitä siitä pääsee tekemään.
- **Tuotanto on ohi ja laskutettu.** Kierroksen 02 laskuruutu on olemassa, mutta
  mitä sivu on sen jälkeen.

Nämä ovat lyhyitä ruutuja. Älä tee niistä isoja.

## Mitä EI suunnitella

Kaikki aiempien kierrosten poisjätöt ovat voimassa.

Tällä kierroksella lisäksi:

- **Ei markkinointia, brändiviestintää eikä uutiskirjettä.** Tuote ei kerro
  itsestään, se kertoo tapahtumasta.
- **Ei viestiä, joka sisältää koko sivun sisällön.** Katso periaate 1.
- **Ei muistutusnumerointia** tyyliin "muistutus 2/3". Se kertoo vastaanottajalle
  että hän voi jättää huomiotta vielä yhden.
- **Ei automaattista viestiä, jota tuottaja ei voi pysäyttää.**
- **Ei tekstiviestejä eikä push-ilmoituksia.** Eri kanava on eri ongelma, ja se
  ratkaistaan erikseen jos ratkaistaan.
- **Ei asetussivua muistutusten säätämiseen.** Säännöt tulevat määräajoista, eivät
  käyttäjän valinnoista.

## Toivotut ulostulot

- Neljä viestityyppiä renderöityinä sähköposteina, vastaanottajineen
- Taulukko: montako viestiä yksi tilaaja saa yhden tuotannon aikana, ja mistä
  jokainen johtuu
- Tuottajan näkymä siihen, mikä on lähdössä, ja pysäytys
- "Mikä muuttui" merkintänä sivulla, 390
- Kolme päättymisruutua, 390
- Yksi itsenäinen HTML-tiedosto
- Lyhyt perustelu kahdesta asiasta: miten oletuksen laukeamisen sävy ratkaistiin,
  ja millä säännöllä muutos ansaitsee viestin
- Loppuun lista siitä, mitä huomasit puuttuvan mutta et suunnitellut
