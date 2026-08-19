# Mockupit

Visuaaliset luonnokset ja niiden promptit. Mockup ja se prompti, jolla se syntyi,
pysyvät samassa kansiossa, koska prompti on se osa jota muokataan seuraavalla
kierroksella.

## Rakenne

Jokainen kierros saa numeroidun kansion:

```
mockups/
  01-asiakas-ja-tuottaja/
    prompti.md          Syöte, jolla mockup tehtiin
    ...                 Viedyt tiedostot (HTML, PNG, PDF)
    muistiinpanot.md    Mikä toimi, mikä ei, mitä muutetaan seuraavaksi
```

Numerointi on kronologinen, ei prioriteettijärjestys. Vanhoja kierroksia ei
poisteta, koska hylätty suunta on tietoa siinä missä hyväksyttykin.

## Esimerkkidata

**Kaikki mockupeissa esiintyvät nimet, tapahtumat, päivämäärät ja summat ovat
keksittyjä.** Repo on julkinen. Todellisia asiakkaita, tuotantoja, hinnastoja tai
sopimusehtoja ei käytetä mockupeissa edes esimerkkinä.

Yhtenäisyyden vuoksi kaikki kierrokset käyttävät samaa keksittyä tuotantoa,
joka on kuvattu kierroksen 01 promptissa. Näin eri näkymiä voi verrata keskenään.

## Tiedostomuodot

Versionhallintaan sopivat HTML-viennit ja kohtuukokoiset PNG:t. Isot binäärit,
videot ja suunnittelutyökalujen raakatiedostot jäävät repon ulkopuolelle.

## Suhde dokumentteihin

Mockup ei ole päätös. Jos luonnos paljastaa, että jokin konseptin osa ei toimi
käytännössä, muutos kirjataan `docs/`-kansioon ja mockup tehdään uudestaan.
Dokumentit ovat totuus, mockupit ovat kokeiluja.
