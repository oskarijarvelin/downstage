# Downstage

Teknisen tapahtumatuotannon asiakasrajapinta.

Downstage on konsepti alustalle, joka hoitaa sen osan tapahtumatuotannosta, jossa
tekniikka kohtaa asiakkaan: briefin, tarjouksen, aikataulun, muutokset,
päätökset ja jälkihoidon. Se ei ole kalustorekisteri eikä projektinhallintatyökalu.
Ne ovat jo olemassa, ja ne ratkaisevat tuotantoyhtiön sisäisen puolen.

## Ydinteesi

Tapahtumatuotannon vaikein ongelma ei ole kaluston hallinta. Se on kääntäminen.

Asiakas puhuu tapahtumasta. Tekniikka elää patchissa, riderissa, virrankulutuksessa
ja miehityksessä. Näiden välissä on ihmistuottaja, joka kääntää käsin, sähköpostilla,
ja jonka työajasta suuri osa kuluu tiedon perässä juoksemiseen.

Downstage mallintaa molemmat puolet samaan dataan ja renderöi sen kahdesti:
teknisenä sisäänpäin, asiakkaan kielellä ulospäin.

## Kolme periaatetta

**Yksi linkki per tapahtuma.** Asiakas ei kirjaudu järjestelmään eikä opettele
työkalua. Yksi pysyvä osoite, joka on se tapahtuma, briefistä loppuraporttiin.

**Taso ilmestyy vasta kun sitä on kaksi.** Sama tuote taipuu tunnin tilaisuudesta
viikon festivaaliin, koska monimutkaisuus ilmestyy silloin kun data vaatii sitä,
ei silloin kun käyttäjä kääntää kytkintä.

**Kaikki muut ehdottavat.** Ainoa oikeus, jolla on merkitystä, on oikeus sitoa rahaa.
Kaikki muu on ehdotus, joka menee muutoslokiin odottamaan hyväksyntää. Siksi pääsyn
kanssa voi olla antelias.

## Dokumentit

| Tiedosto | Sisältö |
| --- | --- |
| [docs/konsepti.md](docs/konsepti.md) | Ongelma, markkina-aukko, periaatteet, toiminnallisuudet, tekoälyn rooli |
| [docs/tietomalli.md](docs/tietomalli.md) | Entiteetit, muutosloki, osapuolet ja mandaatti, jäljitettävyys |
| [docs/mvp.md](docs/mvp.md) | Testattava hypoteesi, vaiheistus ja mittarit |

## Tila

Konsepti. Ei koodia, ei aikataulua, ei lupausta siitä että tämä toteutetaan.
Tämä repo on ajattelun paikka, ja dokumentit muuttuvat kun ajattelu muuttuu.

## Nimestä

Downstage on lavan etuosa, se reuna joka on kääntynyt yleisöä kohti. Tuote on
teknisen tuotannon downstage-puoli: se osa, joka näkyy asiakkaalle.

## Huomautus sisällöstä

Tämä repo on julkinen. Se sisältää vain yleistä konseptisuunnittelua.
Täällä ei ole asiakasnimiä, hinnoittelua, budjettilukuja, sopimusehtoja
eikä minkään tuotantoyhtiön tai tilaajan sisäistä materiaalia, eikä sellaista
tänne lisätä.
