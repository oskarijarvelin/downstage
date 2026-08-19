# Kierros 02: muistiinpanot

Arvio 19.8.2026. Seitsemän tiedostoa renderöity headless-selaimella, rajaukset
tarkistettu koneellisesti, ja renderöity DOM luettu tekstinä sisällön arviointia
varten.

## Tila: vienti taas vajaa, ja syy on rakenteellinen

`support.js` puuttuu jälleen, nyt kansiosta `02-muutoksen-elinkaari/`.
Kaikki seitsemän tiedostoa viittaavat siihen.

Kokeilin kopioida kierroksen 01 `support.js`:n tilalle. Sivut käynnistyvät, mutta
neljässä näkymässä taulukkorivit jäävät tyhjiksi (vaiheet 2, 3, 5 ja 6). Eli
kierroksen 01 tukitiedosto ei kelpaa korvaajaksi, vaan kierroksen 02 oma pitää
viedä.

**Tätä tärkeämpi havainto:** `.dc.html` lataa ajonaikaisesti Reactin, ReactDOMin ja
Babelin unpkg.com:sta ja fontit Google Fontsista. Kierroksen 02 vaatimus
"itsenäinen HTML ilman ulkoisia riippuvuuksia" on siis mahdoton tässä
vientimuodossa, eikä kyse ollut ohjeen sivuuttamisesta. Vaatimus oli väärin
kirjoitettu, ei väärin noudatettu.

Käytännön seuraus: nämä tiedostot eivät aukea ilman verkkoyhteyttä, eivätkä
välttämättä enää vuosien päästä, jos CDN-osoitteet muuttuvat. Arkistokelpoisuus ei
ole ratkaistu.

Vaihtoehdot kierrokselle 03:

1. Pyydä työkalulta staattinen HTML-vienti ilman React-ajonaikaa, jos sellainen on
2. Hyväksy `.dc.html` ja `support.js` parina ja vie molemmat aina yhdessä
3. Ota renderöidystä sivusta staattinen tilannevedos ja tallenna se arkistoversioksi

Vaihtoehto 3 on varmin, koska se ei ole työkalun ominaisuuksien varassa.

## Rajaukset

Kaikki kahdeksan kieltoa pitivät kaikissa seitsemässä tiedostossa. Mukana oli myös
tämän kierroksen uusi kielto: käyttöliittymässä ei saa olla vaihepalkkia eikä
"vaihe 3/6" -tyyppistä merkintää. Elinkaari-koontisivulla vaiheet näkyvät, mutta
se on mockupin esitystapa eikä tuotteen komponentti, kuten promptissa sallittiin.

Sana "lava" esiintyy vastapuolen aikataulurivillä ("Lava vapaa teille"). Se on
oikein: kielto koski lavaa rakenteellisena tasona ja navigaationa, ei fyysistä
lavaa aikataulutekstissä.

## Mikä onnistui

**Vastapuolen näkymä ratkaisi pääsykysymyksen oikein.** Se on sama
asiakasrenderöinti rajattuna omaan slottiin, ei neljäs käyttöliittymä. Pois jäivät
kokonaisbudjetti, muut esiintyjät, tuotannon muut päätöskohdat ja tilaajan
yhteystiedot. Alalaidassa lukee suoraan, että linkki näyttää vain oman esityksen
tiedot. Tämä on todiste siitä, että objektipuuhun perustuva rajaus riittää eikä
roolimatriisia tarvita.

Näkymässä on myös lause, joka kannattaa säilyttää tuotteeseen asti:
"Lataus ei ole päätös. Jos versio vaatii lisää tekniikkaa, siitä syntyy
muutosehdotus, jonka tilaaja hyväksyy tai hylkää."

**Mallin arvio ja tuottajan hinta erotettiin kahdeksi sarakkeeksi**, ei kahdeksi
tilaksi samassa kentässä. Arvio on katkoviivalla, harmaana ja etumerkillä ≈, ja
sen alla lukee "malli, ei sitova". Ennen hinnoittelua tuottajan sarakkeessa ei ole
lukua vaan toiminto, joten valmista hintaa ei ole olemassa missään vaiheessa.

Lisäksi mockup teki valinnan, jota ei pyydetty: mallin arvio on tarkoituksella eri
kuin tuottajan lopullinen hinta. Se on oikea opetus katsojalle.

**Epäonnistunut parsinta on käsitelty perusteellisemmin kuin pyydettiin.**
Skannattu liite ilman tekstikerrosta, tila `parsimatta`, tiiviste näkyvissä,
alkuperäinen säilyy, ja kolme toimintoa: avaa liite, kirjaa rivit käsin, pyydä
luettava versio. Näkymässä lukee, ettei malli tuottanut yhtään riviä eikä
ehdottanut arvausta, ja että käsin kirjattu rivi on kelvollinen lopputulos.

**Seuraukset esitetty molemmilla kielillä.** Tuottajan puolella laskenta ajettiin
uudelleen ja näkyviin tulivat miehitystunnit, huippukulutus ja päivitetty
kuormalista, alla teksti "laskenta on koodia, ei mallia".

Aikataululogiikka meni oikein: soundcheck piteni 45 minuutista 75:een, joten se
alkaa 30 minuuttia aiemmin eikä lopu myöhemmin. Sitä ei kerrottu promptissa.

**Lasku sulkee kierroksen 01 silmukan.** Laskuerittelyssä lukee "oletus ei
laukennut" ja perustelu: ohjelma vahvistettiin kolme päivää ennen määräaikaa,
joten versio 4 ei jäänyt voimaan oletuksena. Päätöskohta suunniteltiin kierroksella
01 ja se saa päätöksensä kierroksella 02.

## Kolme asiaa, jotka viedään dokumentteihin

**1. Mallin arvio omaksi kentäkseen.** `muutos`-tauluun `kustannusarvio` erilleen
kentästä `kustannusvaikutus`. Sääntö: hinnoittelematon rivi ei näy tilaajalle
eikä vaikuta laskentaan. Tämä puuttui tietomallista kokonaan.

**2. `slot.nakyy_asiakkaalle`.** Kierroksen 01 keksintö, joka on nyt käytössä myös
kierroksella 02. Oletusarvo slotin tyypistä: tekniset piiloon, ohjelmalliset
näkyviin.

**3. Osittain onnistunut parsinta.** Yksi lataus voi onnistua osittain: rider v2:n
luettavasta osasta syntyi kolme muutosriviä, ja skannattu liite jäi käsin
luettavaksi. `lahde_dokumentti.tila` tarvitsee siis arvon `osittain_parsittu`, ja
`docs/tiedostot.md` väittää tällä hetkellä implisiittisesti, että lataus joko
onnistuu tai ei.

Kolmas on aito löydös. Se ei tullut esiin kirjoittamalla, vaan siitä että joku
joutui piirtämään ruudun.

## Kierros 03

Ennen uutta kierrosta kannattaa päivittää dokumentit yllä olevalla kolmella
kohdalla, jotta seuraava prompti voi taas nojata niihin.

Vientivaatimus kirjoitetaan uusiksi: ei "itsenäinen HTML", vaan "vie `support.js`
mukana samaan kansioon" plus erikseen otettu staattinen arkistovedos.
