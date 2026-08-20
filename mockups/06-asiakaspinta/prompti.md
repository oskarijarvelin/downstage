# Prompti kierros 06: asiakaspinnan koherenssi ja ensimmäinen hetki

Syöte Claude Designille. Liitä repo mukaan kontekstiksi.

---

## Lue ensin

1. `mockups/01-asiakas-ja-tuottaja/` kokonaisuudessaan. **Asiakasnäkymä on
   suunniteltu siellä eikä sen jälkeen uudelleen.**
2. `mockups/04-tuottaja-mobile/suunnitelma.md`. Sama kuri, nyt toiselle pinnalle.
3. `mockups/02`, `03` ja `05` muistiinpanot
4. `docs/konsepti.md`, `docs/tietomalli.md`, `docs/tiedostot.md`
5. `docs/mvp.md`, erityisesti vaihe 0

## Vienti

Kuten kierroksilla 04 ja 05: yksi itsenäinen HTML-tiedosto, ei ulkoisia
viittauksia.

## Lähtötilanne

Tuottajan pinta jäsennettiin kierroksilla 04 ja 05: yksi kortti, yksi jono,
järjestyssääntö näkyvissä, konteksti tilan mukaan.

**Asiakkaan pintaa ei ole katsottu uudelleen kierroksen 01 jälkeen.** Sen jälkeen
tuotteeseen on lisätty kustannusarvio erillään hinnasta, osittainen parsinta,
mandaattikatto ja eskalointi, muutospyynnön lähetys, tarkennuskysymys ja
korttimalli. Osa näistä on piirretty asiakkaan puolelle kierroksilla 02 ja 03,
mutta aina yhden vaiheen ruutuna, ei osana kokonaisuutta.

Oletus on siis, että asiakaspinta on ajautunut. Ensimmäinen tehtävä on selvittää
kuinka paljon.

## Tämä kierros ei lisää toiminnallisuutta

Sama sääntö kuin kierroksella 04. Ainoa poikkeus on kohta A, joka on olemassa
oleva tilanne jota ei vain ole koskaan piirretty.

Jos huomaat muuta puuttuvan, kirjoita se loppuun listaksi äläkä suunnittele sitä.

## A. Ensimmäinen hetki

**Tämä on kierroksen tärkein ruutu.**

Jokainen asiakasmockup tähän asti näyttää tuotannon kesken lennon: muutoksia on
lokissa, päätöskohtia auki, tiedostoja saapunut. Kukaan ei ole piirtänyt sitä
hetkeä, jossa linkki juuri saapui eikä mitään ole vielä tapahtunut.

`docs/mvp.md`:n vaihe 0 sanoo, että koko konseptin kalleimpaan kysymykseen
vastataan sillä, avaako asiakas linkin. **Tämä ruutu on se, jonka hän avaa.**
Jos se ei toimi, mikään muu ei ehdi merkitä mitään.

Suunnittele se: tilaaja on juuri saanut osoitteen, tuotanto on luonnostilassa,
lokissa ei ole yhtään riviä, päätöskohtia ei ole vielä avattu, tiedostoja ei ole
pyydetty.

Kolme asiaa, joihin ruudun pitää vastata heti:

1. **Mikä tämä on ja miksi minä sain sen.** Ei tuoteselostetta.
2. **Mitä minulta odotetaan ja milloin.** Tässä vaiheessa todennäköisesti yksi asia.
3. **Mitä tapahtuu, jos en tee mitään.** Tuotteen oma logiikka, käytettynä
   ensimmäisestä hetkestä asti.

Suunnittele myös se sähköpostin runko, jonka mukana linkki tulee. Se on osa tätä
ruutua, koska se on se mitä asiakas näkee ensin, ja tähän asti sitä ei ole ollut
missään.

Vertailukohta: kierroksen 04 tyhjä jono onnistui, koska se ei ollut tyhjä tila
vaan hetki jolla on sisältö. Tee sama tässä.

## B. Asiakasnäkymän selkäranka

Kierroksen 01 asiakasnäkymä oli yksi sivu ilman navigaatiota, ja järjestys oli:
mitä sinulta odotetaan, päätöskohdat, aikataulu, muutokset, toimitettavat,
yhteystiedot.

Tarkista se kokonaisuutena nyt, kun sisältöä on enemmän, ja korjaa ajautuminen.
Erityisesti:

- **Onko sivu vieläkään luettavissa ylhäältä alas ilman navigaatiota**, kun lokissa
  on 19 riviä ja päätöskohtia on kaksi.
- **Käyttääkö asiakaspinta samaa korttimallia kuin tuottajan pinta**, vai onko
  siellä yhä kierroksen 01 omat rivityypit. Jos malli sopii, käytä sitä. Jos ei
  sovi, kerro perusteluosassa miksi ei, äläkä pakota.
- **Näkyykö seuraus samalla logiikalla.** Tuottajan kortissa on seurausleima, joka
  kertoo mitä tapahtuu ja milloin. Asiakkaalla vastaava on päätöskohdan oletus.
  Ovatko ne sukua toisilleen vai kaksi eri keksintöä.
- **Onko sanasto sama.** Käy läpi jokainen käyttöliittymäteksti ja varmista, ettei
  sama asia ole kahdella nimellä eri pinnoilla.

Näytä kaksi versiota: nykyinen ajautunut ja korjattu, ja merkitse mikä muuttui.

## C. Vastapuolinäkymä linjaan

Kierroksella 02 todettiin, että vastapuoli saa saman asiakasrenderöinnin rajattuna
omaan slottiinsa. Se on kirjoitettu ja piirretty kerran, minkä jälkeen
asiakasrenderöinti on muuttunut.

Tarkista, että väite pitää yhä. Näytä sama korjattu asiakasnäkymä ja sama näkymä
vastapuolelle rajattuna, ja tee näkyväksi tasan se, mikä katoaa rajauksessa.

Jos väite ei enää pidä, sano se. Se on tärkeämpi tieto kuin nätti ruutu.

## D. Jaetut palikat

Yksi sivu, jolla ovat tuotteen jaetut peruspalikat molemmissa renderöinneissä
vierekkäin, asiakas vaaleana ja tuottaja tummana:

- kortti
- vaikutusmerkintä (raha, aika)
- lähdelainaus
- seurausleima ja päätöskohdan oletus
- toimintorivi
- tilamerkinnät (odottaa, hyväksytty, hylätty, eskaloitu, odottaa hinnoittelua)

Tämä ei ole tyylikirjasto vaan tarkistus: **sama asia näyttää samalta molemmilla
puolilla, vaikka väri ja tiheys eroavat.** Jos jokin palikka on olemassa vain
toisella puolella, merkitse se ja kerro miksi.

## Mitä EI suunnitella

Kaikki aiempien kierrosten poisjätöt ovat voimassa: ei kirjautumista, ei chattia
tai yleistä kommentointia, ei kansiopuuta, ei asetuksia tai roolimatriisia, ei
KPI-kortteja tai kaavioita, ei tekoälyassistenttia, ei vaihepalkkia, ei
varmistusdialogeja, ei versiohistorian selainta, ei alanavigaatiopalkkia, ei
hampurilaisvalikkoa, ei muokattavaa kotinäkymää, ei tuotantovalitsinta, ei
tilakytkimiä.

Asiakasnäkymässä lisäksi:

- **Ei navigaatiota.** Yksi linkki on yksi sivu, ja jos sisältö ei mahdu, ratkaisu
  on ankkuri tai laskostus, ei reititys.
- **Ei tervetulokierrosta, opastusta eikä ohjeruutuja.** Katso A: sivun pitää
  selittää itsensä olemalla ymmärrettävä.
- **Ei tuotemarkkinointia.** Asiakas ei osta työkalua, hän osti tapahtuman.

## Toivotut ulostulot

- Ensimmäinen hetki, 390 ja 1440, sekä sähköpostin runko
- Asiakasnäkymä kokonaisuutena, ennen ja jälkeen, 390 ja 1440
- Vastapuolinäkymä linjattuna, 390
- Jaetut palikat -sivu, 1440
- Yksi itsenäinen HTML-tiedosto
- Lyhyt perustelu kahdesta asiasta: mitä ajautumista löytyi ja mitä sille tehtiin,
  ja päättikö korttimalli sopia asiakaspinnalle vai ei
- Loppuun lista siitä, mitä huomasit puuttuvan mutta et suunnitellut
