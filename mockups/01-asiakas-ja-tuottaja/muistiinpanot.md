# Kierros 01: muistiinpanot

Arvio tehty 19.8.2026. Mockupit renderöity headless-selaimella leveyksillä
1440 ja 390, ja rajaukset tarkistettu koneellisesti kaikista kolmesta tiedostosta.

## Tila

**Vienti on vajaa.** Kaikki kolme tiedostoa viittaavat riviin
`<script src="./support.js">`, eikä sitä ole kansiossa. Tiedosto sisältää datan ja
templaattien renderöinnin, joten ilman sitä paikanvaraajat jäävät näkyviin:
asiakasnäkymässä 37 kappaletta, tuottajan näkymässä 59. Asiakasnäkymästä puuttuu
aikataulu kokonaan, ja tuottajan näkymä on käytännössä pelkkiä paikanvaraajia.

Korjaus: vienti uudestaan tukitiedoston kanssa, tai data upotettuna suoraan
HTML:ään. Jälkimmäinen on parempi, koska silloin tiedostot toimivat itsenäisinä
myös repossa ja selaimessa ilman palvelinta.

## Rajaukset

Kaikki seitsemän kieltoa pitivät. Nolla osumaa kolmesta tiedostosta:

- Ei kirjautumissivua
- Ei chattia, kommenttiketjuja eikä yleistä keskustelua
- Ei kansiopuuta eikä tiedostoselainta
- Ei asetuksia, käyttäjähallintaa eikä roolimatriisia
- Ei KPI-kortteja, mittaristoja eikä kaavioita
- Ei tekoälyassistenttia eikä chat-kuplaa
- **Ei lavatasoa.** Sana "lava" ei esiinny rakenteena missään

Viimeinen oli promptiin sisäänrakennettu ymmärrystesti: esimerkkituotannossa on
yksi paikka, joten periaatteen "taso ilmestyy vasta kun sitä on kaksi" mukaan
lavavalitsinta ei saa olla. Testi meni läpi.

## Mikä onnistui

**Riderin muutosten ryhmittely.** Kolme riviä on esitetty yhtenä kokonaisuutena,
jossa on selite samasta latauksesta syntymisestä ja yksi yhteinen toiminto
"Hyväksy kaikki kolme". Tämä oli epävarmin kohta promptissa ja meni tarkasti oikein.

**Eskalointi pyydettyä paremmin.** Mandaattikaton ylittävällä rivillä kerrotaan
kenelle päätös meni, ja perään on lisätty ettei tilaajan tarvitse tehdä tälle
mitään. Sitä ei pyydetty. Se on oikea ratkaisu, koska eskaloitu rivi on juuri se,
joka jää muuten roikkumaan epäselvänä.

**Laskentasääntö käyttöliittymätekstinä.** Tuottajan näkymän alalaidassa lukee,
että virrat, painot ja miehitystunnit laskee laskentakerros eikä malli. Tämä on
`docs/tietomalli.md`:n sääntö 3 nostettuna ruudulle. Parempi paikka sille kuin
dokumentti.

**Muutoslokin ryhmittely tilan mukaan.** Odottaa sinua ensin, sitten hyväksytyt,
sitten hylätyt. Ei aikajärjestyksessä oleva syöte.

**Asiakasnäkymässä ei navigaatiota** ja sivu taittuu puhelimella ilman erillistä
rakennetta.

## Mikä jäi auki

**Päätöskohtakortin tilat.** Kortissa näkyy päällekkäin sekä päätöstä edeltävät
painikkeet että kaksi päätöksen jälkeistä tilaa. Ei pysty sanomaan, onko kyseessä
tarkoituksellinen tilagalleria vai renderöintijäänne, ennen kuin tukitiedosto on
paikallaan. Tarkistettava seuraavassa kierroksessa.

## Havainto, joka viedään tietomalliin

Tuottajan aikatauluun on lisätty oma sarake sille, **näkyykö rivi asiakkaalle.**
Sitä ei ollut promptissa.

Se on hyvä keksintö, koska se tekee kahden näkymän periaatteesta muokattavan
tietokentän eikä suunnittelijan kertapäätöstä. Käytännössä `slot`-tauluun
kenttä `nakyy_asiakkaalle` (bool), ja oletusarvo riippuu slotin tyypistä:
tekniset slotit piilossa, ohjelmalliset näkyvissä.

## Muutokset kierrokseen 02

1. Vaadi promptissa **itsenäinen HTML ilman ulkoisia riippuvuuksia**. Kaikki CSS,
   JS ja data samaan tiedostoon. Tämä olisi estänyt koko yllä olevan ongelman.
2. Pyydä päätöskohtakortista **erilliset ruudut kullekin tilalle** sen sijaan että
   ne ovat samassa näkymässä.
3. Lisää esimerkkidataan yksi tapaus, jossa **parsinta epäonnistui** ja tiedosto
   odottaa käsin lukemista. Se on `docs/tiedostot.md`:n mukainen tila, jota
   ensimmäinen kierros ei kata.
