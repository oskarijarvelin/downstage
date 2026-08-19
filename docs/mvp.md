# MVP ja vaiheistus

## Mitä oikeasti testataan

Hypoteesi ei ole "tällainen työkalu olisi hyödyllinen". Se on liian helppo osoittaa
oikeaksi keskustelemalla ja liian vaikea osoittaa vääräksi.

Testattava väite on tämä:

> Kun asiakas näkee saman totuuden kuin tuottaja, ja jokainen pyyntö kirjautuu
> kustannusvaikutuksineen samaan lokiin, sähköpostien määrä ja jälkikäteiset
> erimielisyydet vähenevät mitattavasti.

Ja sen alla piilevä, huomattavasti riskialttiimpi oletus:

> Asiakas avaa linkin ilman että häntä pitää opettaa tai muistuttaa.

Toinen väite on se, joka kaataa tuotteen jos se on väärä. Siksi se testataan ensin,
ja ilman koodia.

## Vaihe 0: ilman koodia

**Tavoite:** selvittää avaako asiakas linkin.

Ota kahdesta kolmeen omaa keikkaa. Ylläpidä jokaisesta yhtä jaettua sivua käsin.
Sivulla on kolme asiaa, ei enempää:

1. Aikataulu
2. Muutosloki, jossa on päivämäärä, kuka pyysi, ja mitä se maksoi
3. Päätöskohdat: mitä pitää päättää, kuka päättää, mihin mennessä, ja mitä tapahtuu
   jos päätöstä ei tule

Lähetä linkki vastauksena sähköposteihin sen sijaan, että vastaat niihin sisällöllä.
Päivitä sivu käsin. Mittaa.

Tämä maksaa yhden viikonlopun ja vastaa kalleimpaan kysymykseen ennen kuin riviäkään
sovelluskoodia on kirjoitettu. Jos asiakkaat eivät avaa linkkiä, konseptin ydin
on väärä ja loput vaiheet ovat turhia.

## Vaihe 1: yksi linkki

**Ensimmäinen koodi. Rajaus on tässä tärkeämpää kuin ominaisuudet.**

Sisällä:

- Tuotanto, paikka ja slot -rakenne tietokannassa, vaikka käyttöliittymä näyttää
  vain yhden tason
- Aikataulunäkymä
- Muutosloki, johon tuottaja kirjaa muutokset käsin
- Päätöskohdat määräaikoineen ja oletuksineen
- Yksi jaettava linkki per tuotanto, asiakkaalle lukuoikeus
- Automaattinen muistutus lähestyvästä päätöskohdasta

Ei sisällä:

- Kalustorekisteriä
- Hinnoittelumoottoria
- Tarjousta
- Tekoälyä
- Festivaalinäkymää
- Mobiilisovellusta

Miksi juuri tästä eikä riderien lukemisesta: riderien parsinta on sisäinen työkalu.
Se säästää aikaa mutta ei testaa mitään väitettä asiakasrajapinnasta. Sillä
aloittaminen tuottaisi hyödyllisen skriptin ja nolla tietoa.

## Vaihe 2: ehdotukset

Asiakas ei enää lähetä sähköpostia, vaan painaa sivulla "pyydä muutosta".

- Ehdotus menee lokiin tilassa `pyydetty`
- Pyytäjä näkee oman pyyntönsä kustannusvaikutuksen heti
- Hyväksyntä kulkee mandaattikaton läpi ja eskaloituu tarvittaessa
- Kokonaisbudjetti näkyy vain rahamandaatin haltijoille

Tässä vaiheessa muutosloki alkaa täyttyä itsestään, ja siitä tulee ensimmäistä kertaa
laskutuskelpoinen dokumentti.

## Vaihe 3: tekoäly, matalimman riskin kohdasta

Sähköposti sisään, ehdotettu muutosrivi ulos. Kustannusvaikutus arvattuna,
alkuperäinen lause tallessa, tila `pyydetty`, luoja `malli`. Tuottaja hyväksyy tai
hylkää yhdellä klikkauksella.

Tämä on turvallisin mahdollinen paikka aloittaa, koska väärä tulkinta maksaa yhden
klikkauksen eikä yhtään mitään muuta. Ja se on samalla se kohta, jossa jäsentymätön
viestintä muuttuu rakenteiseksi dataksi, eli se mihin koko alusta perustuu.

## Vaihe 4: brief ja tarjous

Vapaa teksti sisään, tarvekartta ja tarjousluonnos ulos. Vaatii alleen
kalustopaketit ja hinnoittelulogiikan, ja juuri siksi se tulee vasta tässä:
hinnoittelu on se kohta, joka on jokaisessa talossa erilainen ja joka estää
geneerisen ratkaisun. Rakenna se ensin yhdelle talolle. Yleistä vasta kun toinen
talo maksaa siitä.

## Vaihe 5: skaala

- Useampi paikka, ja lavatason ilmestyminen käyttöliittymään
- Riderien parsinta
- Karhuamisnäkymä mittarina: montako toimitettavaa sisässä, ketkä ovat myöhässä,
  yksi klikkaus muistutus kaikille
- Keikkapäivänäkymä, offline-first

## Mittarit

Nämä mitataan vaiheesta 0 alkaen, myös silloin kun mittaus on käsin laskemista.

| Mittari | Miksi |
| --- | --- |
| Avasiko asiakas linkin, ja montako kertaa | Ainoa mittari, joka voi kaataa konseptin |
| Sähköpostien määrä per tuotanto | Ydinlupaus |
| Jälkikäteisten erimielisyyksien määrä | "Eikös sovittu" on se kalleimmaksi tuleva ongelma |
| Tunteja tarjouksen tekemiseen | Pienten keikkojen kannattavuus ratkeaa tässä |
| Toimitettavia määräaikaan mennessä, prosentteina | Karhuamisen teho |

Vertailukohta pitää kerätä ennen vaihetta 0, muuten mittareista ei ole mitään hyötyä.
Käytännössä: laske kahden tulevan keikan sähköpostit ja tarjoukseen mennyt aika
etukäteen, ilman että mitään on vielä muuttunut.

## Tekninen suunta

Ei mitään kiinnostavaa. Kaikki kiinnostava on tietomallissa ja rajauksessa.

- Framework, joka on jo hallussa. Tässä ei ole mitään syytä opetella uutta.
- Postgres. Malli on relationaalinen ja siinä on polymorfisia viittauksia,
  joten dokumenttikanta tekisi tästä turhan vaikeaa.
- **Ei auth-palvelua.** Sidosryhmillä ei ole tilejä, se on koko idea. Pääsy on
  allekirjoitettu, vanheneva token per `paasy`-rivi. Clerkin tai vastaavan
  käyttöönotto tässä olisi merkki siitä, että periaate 3.4 on unohtunut.
- Sähköposti sisään vaatii vastaanottavan osoitteen per tuotanto. Se on vaiheen 3
  ongelma, ei aiempi.

## Suurimmat riskit

**1. Asiakas ei avaa linkkiä.** Vaihe 0 vastaa tähän suoraan, halvalla ja aikaisin.

**2. Ainoa käyttäjä on tuottaja itse.** Jos asiakas ei ehdota mitään sivulla vaan
lähettää silti sähköpostia, tuote on kallis muistiinpanosovellus. Mittari "sähköpostien
määrä" paljastaa tämän vaiheessa 2.

**3. Hinnoittelu ei yleisty.** Todennäköisin syy sille, ettei tästä tule tuotetta
yhdelle talolle rakennetun työkalun lisäksi. Ei ratkaistavissa etukäteen,
mutta lykättävissä vaiheeseen 4, jolloin siihen mennessä tiedetään onko muu osa
konseptista edes oikein.

**4. Ala ostaa hitaasti ja katteet ovat ohuet.** Tämä ei ole tekninen riski eikä
korjattavissa koodilla. Se vaikuttaa siihen, kannattaako tätä koskaan viedä
tuotteeksi vai pitää se oman työn työkaluna, joka maksaa itsensä takaisin säästettynä
aikana. Molemmat ovat kelvollisia lopputuloksia, mutta ne pitää erottaa toisistaan
ennen vaihetta 4.
