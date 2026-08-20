# Kierros 05: muistiinpanot

Arvio 20.8.2026. Seitsemän välilehteä renderöity ja luettu, rajaukset tarkistettu
renderöidystä sisällöstä.

## Vienti ja rajaukset

Yksi itsenäinen tiedosto, ei ulkoisia viittauksia, ei virheitä. Kaikki rajaukset
pitivät, mukaan lukien tämän kierroksen kolme uutta: ei tuotantovalitsinta, ei
tapahtumapäivätilan kytkintä, ei paikkatasoa muualla kuin ruudussa B4.

Mikään pyydetty ruutu ei jäänyt pois, ei myöskään B4, joka oli merkitty
pudotettavaksi jos kierros käy isoksi.

## Kohdistus: perustelu on parempi kuin ratkaisu

Automaattinen kohdistus perusteltiin näin:

> "Koska suodatus ei vaihda järjestyssääntöä, käyttäjä ei voi menettää mitään
> sillä että jono on kohdistettu, ja siksi se voi tapahtua ilman lupaa."

Tämä on se, mikä tekee automaattisesta käyttäytymisestä hyväksyttävää. Ohjelma saa
tehdä päätöksen käyttäjän puolesta silloin, kun päätöksestä ei voi seurata
menetystä. Sama testi kannattaa muistaa muissakin kohdissa, joissa tuote toimii
itsestään.

## Löydös tietomalliin: uusi tuotannon tila

Ryhmittelyn vaihdon laukaisee tila, ei kalenteripäivä:

> "Kun aikataulun ensimmäinen slot alkaa, tuotanto siirtyy tilaan
> «kasaus käynnissä», ja jono ryhmittyy kellon mukaan."

`docs/tietomalli.md`:n `tuotanto.tila` on tällä hetkellä luonnos, tarjottu,
vahvistettu, ajettu, laskutettu. Väliin tarvitaan tila, joka kattaa kasauksen,
ohjelman ja purun. Ilman sitä ryhmittelyn vaihdolla ei ole mitään mihin tarttua.

Sama tila on todennäköisesti se, joka myös kytkee kohdistuksen päälle, eli yksi
kenttä ratkaisee molemmat tämän kierroksen kysymykset.

## B4: skaalautuvuusväite on vihdoin piirretty

Väite "sama tuote taipuu tunnin tilaisuudesta viikon festivaaliin" on ollut
dokumenteissa alusta asti todistamattomana. Nyt se on ruudulla, ja ratkaisu on
parempi kuin miten säännön itse kirjoitin.

**Paikkataso ilmestyi kentäksi, ei navigaatioksi.** Lava on kortin merkintä ja
taulukon sarake. Lavavalitsinta ei ole, eikä lavakohtaista näkymää.

Myös järjestyssääntö selvisi käännöksestä: kysymys vaihtui muotoon "mikä on rikki,
missä, ja kuka on vapaana", mutta järjestys on edelleen sama periaate, "mikä
keskeyttää ohjelman aikaisimmin".

"Kuka on vapaana" on määritelty laskennallisesti: henkilöllä ei ole omaa slottia
seuraavan 30 minuutin sisällä. Se on johdettavissa slot-datasta, eli se kuuluu
laskentakerrokseen eikä ole erillinen ylläpidettävä tila.

## Puuttuvien lista

Mockup listasi seitsemän kohtaa. Kolme on merkittäviä:

**Kaksi tuotantoa samana tapahtumapäivänä.** Kumpi kohdistus voittaa. Tämä on
käytännössä yleinen tilanne eikä reunatapaus.

**Vuoronvaihto kesken tapahtumapäivän.** Ongelmanapin vastaanottaja vaihtuu kesken
illan, eikä nykyinen malli tunne vuoroa lainkaan.

**Festivaalin monipäiväisyys.** Mitä jono tekee päivien välisenä yönä, kun tuotanto
on tilassa "käynnissä" mutta mitään ei tapahdu.

Kaksi kohtaa on kierroksen 04 listalta yhä auki: ilmoitus jonon muuttumisesta
ruudun ollessa auki, ja summan syöttö yhdellä kädellä.

## Mitä tästä seuraa

Tuottajan pinta on nyt kahden kierroksen jäljiltä jäsentynyt. **Asiakkaan pintaa ei
ole tarkasteltu uudelleen kierroksen 01 jälkeen**, vaikka sen jälkeen on lisätty
kustannusarvio, osittainen parsinta, mandaattikatto, muutospyynnön lähetys,
tarkennuskysymys ja korttimalli. Todennäköisyys sille, että se on ajautunut, on
suuri, ja se on `mvp.md`:n mukaan se pinta, joka testataan ensimmäisenä oikeilla
keikoilla.

Kierros 06 tekee asiakaspinnalle sen, minkä kierros 04 teki tuottajan pinnalle.
