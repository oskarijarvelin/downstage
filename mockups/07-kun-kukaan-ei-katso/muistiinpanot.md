# Kierros 07: muistiinpanot

Arvio 20.8.2026. Kuusi välilehteä renderöity ja luettu.

## Vienti

Yksi itsenäinen tiedosto, ei ulkoisia viittauksia, ei virheitä.

## Määrän budjetti: pyydetty vaatimus tuotti parhaan tuloksen

Vaatimus oli laskea, montako viestiä yksi tilaaja saa yhden tuotannon aikana.
Vastaus: **yhdeksän viestiä 77 vuorokaudessa**, keskimäärin yksi yhdeksän päivän
välein, tiheimmillään kolme viikolla ennen tapahtumaa.

Karsintalista on pidempi kuin lähetettävien lista, ja se on kierroksen tärkein
sivu. Pois jäivät muun muassa jokainen hyväksytty muutos erikseen (9 viestiä,
"hänen oma päätöksensä, ei uutta tietoa"), jokainen saapunut tiedosto (4), kolmas
ja neljäs määräaikamuistutus (3, "kolmas kertoo että kaksi sai ohittaa") ja
viikoittainen tilannekatsaus (11, "tuote kertoisi itsestään, ei tapahtumasta").
Ilman karsintaa luku olisi 19.

Ja se perustelu, joka tekee luvusta puolustettavan: **viisi yhdeksästä viestistä
tilaaja olisi saanut ilman Downstagea, koska tuottaja olisi kysynyt samat asiat
käsin.** Nettolisäys on neljä viestiä yhdessätoista viikossa, ja vastineeksi
tuottaja ei soita kysymään samoja asioita.

Kattoluvut: enintään yksi viesti vuorokaudessa vastaanottajaa kohti, enintään
kaksi määräaikaviestiä päätöskohtaa kohti, ei viestiä samasta asiasta 48 tunnin
sisällä.

## Oletuksen laukeamisen sävy

Neljä sääntöä, ja ne kannattaa säilyttää sanatarkkoina:

1. Viesti kertoo mitä tapahtui, ei kenen takia. Passiivi on tässä tarkkuutta eikä
   pehmentelyä, koska laukeamisen aiheutti määräaika jonka molemmat hyväksyivät.
2. Sanamuoto on sama kuin sopimusehdossa alun perin, sanasta sanaan. Viestissä ei
   ole uutta tietoa eikä uutta tulkintaa.
3. Viesti kertoo heti mitä nyt voi tehdä, ja se on aito polku eikä lohdutus.
4. Ei anteeksipyyntöä eikä sanaa "valitettavasti", koska anteeksipyyntö vihjaisi
   että tuote teki jotain väärin, ja silloin seuraava oletus tuntuisi ansalta.

Sävyn testi: **voiko tuottaja lähettää tämän ihmiselle, jonka kanssa hän tekee
töitä myös ensi vuonna.**

## Sääntö sille, milloin muutos ansaitsee viestin

Johdettu muutoslokista, ei valittu asetuksista. Viesti lähtee kolmesta syystä:
rivi odottaa juuri tätä vastaanottajaa päätöksenä, rivi muuttaa hänen omaa
aikaansa tai rahaansa yli sovitun rajan, tai määräaika liikkui. Kaikki muu on
merkintä sivulla.

Tulvan estää kolme mekanismia, joista kolmas on paras:

> "Jos vastaanottaja kävi sivulla muutoksen jälkeen, viesti perutaan itsestään,
> koska hän on jo nähnyt sen: merkintä sivulla on ensisijainen kanava ja viesti on
> vain varmistus siltä varalta ettei hän tule."

Tämä on yhden linkin periaate vietynä ilmoitusjärjestelmään. Viesti ei kilpaile
sivun kanssa vaan palvelee sitä.

## Dokumenttimuutokset, jotka tästä seuraavat

`docs/konsepti.md` 4.5 sanoo tällä hetkellä vain, että muistutukset lähtevät
automaattisesti. Nyt mekanismi on suunniteltu, ja kolme asiaa kuuluu kirjoittaa
dokumentteihin:

1. **Sääntö sille, milloin viesti lähtee**, ja kattoluvut
2. **Periaate "merkintä sivulla on ensisijainen kanava, viesti on varmistus"**
3. **Se, että päätöskohdan oletusteksti siteerataan viestissä sanatarkkana.**
   `paatoskohta.oletus_kuvaus` on siis sopimustekstiä eikä käyttöliittymäkopiota,
   ja se pitää kirjoittaa sillä ajatuksella.

## Puuttuvien lista

Seitsemän kohtaa, ja ne ovat nyt luonteeltaan reunatapauksia eivätkä aukkoja:
viestin perillemeno, "älä muistuta tästä enää" ilman asetussivua, viestin kieli
kun vastapuoli on ulkomainen, pysäytyksen peruminen määräajan jälkeen, päättäjän
poissaolo, loppuraportti, ja jonon muuttuminen ruudun ollessa auki.

Kaksi ansaitsee huomion myöhemmin: **viestin kieli** on festivaaleilla arkipäivää,
ja **loppuraportti** on ainoa asia, johon jo piirretty ruutu viittaa mutta jota ei
ole olemassa.

## Havainto suunnasta

Seitsemän kierrosta on suunnitellut tuotteen päästä päähän. Puuttuvien listat
ovat muuttuneet aukoista reunatapauksiksi, mikä on merkki siitä että pinta on
katettu.

`docs/mvp.md`:n vaihe 0 on edelleen tekemättä. Se sanoo, että kalleimpaan
kysymykseen vastataan ylläpitämällä yhtä sivua käsin kahdella oikealla keikalla,
ja että se maksaa yhden viikonlopun. Kahdeksas suunnittelukierros ilman yhtäkään
mittausta olisi täsmälleen se virhe, jota vastaan mvp.md kirjoitettiin.

Siksi kierros 08 ei suunnittele tuotetta vaan sen, millä tuote testataan.
