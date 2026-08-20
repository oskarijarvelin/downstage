# Kierros 04: muistiinpanot

Arvio 20.8.2026. Kaikki kuusi välilehteä renderöity ja luettu tekstinä, rajaukset
tarkistettu renderöidystä sisällöstä eikä lähdekoodista.

## Vienti

Kunnossa. Yksi 173 kilotavun itsenäinen tiedosto, nolla ulkoista viittausta, nolla
paikanvaraajaa. Vientiongelma, joka vaivasi kierroksia 01 ja 02, on ratkennut.

## Rajaukset

Kaikki yksitoista kieltoa pitivät, mukaan lukien tämän kierroksen neljä uutta.
**Alanavigaatiopalkkia ei ilmestynyt**, mikä oli se yksittäinen riski jonka takia
se kirjoitettiin promptiin.

## Diagnoosi piti

Neljä paneelia purkautui yhdeksi jonoksi, joka on jaettu kolmeen nimettyyn ryhmään.
Sama korttimalli palvelee kaikkia neljää tietotyyppiä. Muutos näyttää nyt samalta
joka paikassa, jossa se esiintyy.

## Mikä onnistui

**Järjestyssääntö on luettavissa kolmesta paikasta.** Ryhmän otsikko, otsikon alla
oleva sääntöteksti, ja kortin oma seurausleima ylhäällä oikealla. Leima on **sama
teksti, jolla kortti sijoittui ryhmäänsä**: "oletus laukeaa 11.4.", "estää
läpimenon 16:30", "odottanut 19 pv". Lajitteluavain on siis näkyvissä itse
kohteessa, eikä järjestystä tarvitse selittää erikseen.

**Tyhjä jono ansaitsi hetkensä.** "Kaikki päätökset on tehty ja jokainen määräaika
on kiinni", ja sen alla mitä on kunnossa, seuraava määräaika jota kukaan ei ole
vielä myöhästynyt, ja päivän kulku. Ruutu esittää saman tuotannon myöhemmässä
tilassa (T-2, versio 5), mikä sitoo sen muuhun aineistoon.

**Katselmuspinnan myönnytys tehtiin rehellisesti.** Tarvelista on leveänä
kahdeksan saraketta ja laskentarivi, ja 390 pikselissä se sanoo suoraan olevansa
parempi koneella, antaa tiivistelmän ja tarjoaa ne kaksi toimintoa jotka oikeasti
onnistuvat puhelimella. Ruudun päättävä lause tiivistää koko kierroksen:

> "Ehdotetut rivit ovat kortteja, ja kortti toimii puhelimessa. Taulukko ei."

**Kaksi dokumenttisääntöä näkyy taas käyttöliittymätekstinä.** Laskentarivillä
lukee "vahvistetut rivit, ehdotetut eivät ole mukana", ja päivän kulussa yksi rivi
on merkitty piilotetuksi, eli `slot.nakyy_asiakkaalle` on käytössä.

## Kolme aukkoa, jotka jäivät

Mockup listasi itse kuusi asiaa, jotka se huomasi puuttuvan mutta ei suunnitellut,
kuten prompti pyysi. Kolme niistä on olennaisia.

**1. Tapahtumapäivä.** Järjestyssääntö on suunniteltu päivien mittakaavassa.
Tapahtumapäivänä kaikki määräajat ovat tunteja, ja kolme ryhmää todennäköisesti
romahtavat yhdeksi. Tämä on suurin aukko, koska se on juuri se hetki, jona
puhelinta oikeasti käytetään.

**2. Offline.** Jono on se näkymä, jonka haluaisi eniten toimivan hallissa ilman
verkkoa, eikä se degradoidu siististi ilman että se on suunniteltu.

**3. Useampi rinnakkainen tuotanto.** Konteksti on nyt yhden tuotannon rivi.
Käytännössä keikkoja on kesällä useita päällekkäin, joten yhden tuotannon jono ei
riitä. Tämä on rajaus, joka pitää ratkaista ennen kuin työkalua voi käyttää omassa
työssä.

## Kierros 05

Kohdat 1 ja 3 kuuluvat yhteen: molemmat kysyvät, mikä on jonon konteksti. Ne
kannattaa suunnitella samalla kierroksella, ja se on luonteva jatko myös siksi,
että keikkapäivänäkymä on ollut listalla vaiheesta 5 asti mutta aina siirretty.

Kohta 2 on enemmän tekninen kuin visuaalinen, ja se kuuluu `docs/tietomalli.md`:n
avoimiin kysymyksiin, jossa se jo on.
