# weather

### Ominaisuudet
- Toimii käyttäjän laitteella Javascriptilla.
- Käyttää yhtä html tiedostoa. Kansio symbolikuville ja tyylitiedostolle. Erillinen piilotettu JS-tiedosto joka palauttaa FMI-API avaimen.
- Vaatii HTTPS-yhteyden HTML5 Geolocationin käyttöä varten.


### Käytetyt kirjastot
- HTML5 Geolocation (Koordinaattien selvitys)
- Google Geocoder API (Kaupungin nimen selvitys koordinaateilla)
- Jquery 3.2.1 (Käyttöliittymä)
- Jquery Mobile 1.5.0 Alpha 1 (Näytön asennon selvitys)
- Bootstrap 4 (Käyttöliittymä)
- Popper (Bootstrap 4 vaatimus)
- Ilmatieteenlaitoksen avoimen datan palvelu (Sääennusteet)


### Toiminnot
- Ohjelma hakee käyttäjän sijainnin ja sen perusteella seuraavan 36 tunnin säätiedot lähimmältä sääasemalta.
- Joka tunnilta näytetään ennustettu lämpötila ja sääsymbolin kuva.
- Sääsymboleiden selitteet ovat myös saatavilla painamalla kuvaa.
- Responsiivinen käyttöliittymä.
- Mobiililaitteilla huomioitu puhelimen asento. Puhelimen ollessa poikittain näytetään 6 ruutua yhdellä rivillä. Pystyasennossa säätiedot ovat peräkkäin.


### Parannettavaa

- Javascript itsessään helpoin ratkaisu demotilanteessa, mutta ei toimiva tuotannossa.
- Ongelmana API avainten joutuminen käyttäjien käsiin.
- Ongelma API skaalautuvuudessa, johtuen API kyselyiden rajoitetusta määrästä.


Ratkaisuna ongelmiin voisi olla palvelimella pyöritettävä raskaampi ohjelmisto. Yhdellä kyselyllä on mahdollista saada kaikkien sääasemien ennusteet. Tämä kuitenkin vaatii huomattavasti enemmän laskentatehoa ja muistia (Kysely kaikilla kaupungeilla kaatoi selaimen). Tämä yksittäinen kysely kuitenkin ratkaisisi skaalautuvuuden ja API avain ei joutuisi käyttäjille. Ongelmana olisi pyöriteltävän datan koko ja lähimmän sääaseman selvitys olisi toteutettava itse. Kaupungin selvittämisen voisi puolestaan ratkaista suorittamalla haut kaikille sääasemille ja asettamalla niille kaupungit erillisessä tiedostossa, jotta niitä ei haeta jokaista kyselyä varten erikseen. Lopputuloksena olisi tietoturvallisempi, mutta enemmän palvelimelta vaativa ratkaisu.


#### Bugit (Testattu: FF(desktop/android), Vivaldi(desktop), Chrome(desktop,android)):

- Puhelimen GPS:n ollessa pois päältä ei saada virhettä ja tiedot eivät tulostu (Mobiilitestausta hankala suorittaa)


Sääsymbolit peräisin Ilmatieteen laitoksen sivuilta (http://ilmatieteenlaitos.fi/saamerkkien-selitykset)
