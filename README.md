# ApacheWebTask6

## x)

- Nimipohjainen virtuaalinen hosting (isännöinti) ja IP-pohjainen virtuaalinen hosting ovat kaksi tapaa käsitellä useita verkkotunnuksia yhdellä verkkopalvelimella.

- IP-pohjaisessa virtuaalisessa hostaamisessa palvelin käyttää yhteyden IP-osoitetta määrittääkseen, ketä virtuaalista hostia palvellaan, kun taas nimipohjaisessa virtuaalisessa isännöinnissä palvelin luottaa siihen, että asiakas ilmoittaa isäntänimen osana HTTP-headeriä.

- Nimipohjainen virtuaalinen hosting on yleensä yksinkertaisempaa ja helpottaa niukkojen IP-osoitteiden kysyntää, joten se on suositeltavin vaihtoehto.

- Nimipohjainen virtuaalinen hosting perustuu IP-pohjaiseen virtuaalisen hostin valinta-algoritmiin, mikä tarkoittaa, että oikean palvelinnimen haku tapahtuu vain niiden virtuaalisten hostien välillä, joilla on paras IP-pohjainen osoite.

- Nimipohjaisen virtuaalihostingin käyttöönottamiseksi sinun on luotava jokaiselle isännälle <VirtualHost>-lohko, jossa on vähintään ServerName-direktiivi ja DocumentRoot-direktiivi.

## a)

Tässä nykyisen etusivun lähtöpisteestä kuva: 

![kuva](https://user-images.githubusercontent.com/105205141/216953462-8d821d88-c5ff-42cf-8a26-8ee12e28b2fd.png)

Tämän jälkeen avasin terminaalin ja etsin oikean hakemiston, jossa varmuuskopioin palvelimen Index-sivun ja muokkasin sivua seuraavanlaiseksi seuraavanlaisilla komennoilla:

![kuva](https://user-images.githubusercontent.com/105205141/216953715-077ba02c-3692-4b3b-b21f-b5a5212d7aad.png)

 Nano-komennon jälkeen kirjoitin index.html tiedostoon: 

        <!DOCTYPE HTML>
        <html>
        <head>
        <title> New Frontpage </title>
        <meta charset="utf-8"/>
        </head>
        <body>
        <h1> Welcome to the new frontpage of this web server! </h1>
        </body>
        </html>
        
   Jonka jälkeen tallensin painamalla (CTRL + X => Y => ENTER)
 
 uudelleenkäynnistettyäni palvelimen sivu näytti tältä: 
 
 ![kuva](https://user-images.githubusercontent.com/105205141/216954210-db21666a-95ec-413b-8bbb-fe1ee9457668.png)
 
 Annoin myös oikeudet ei-sudo käyttäjille kirjoittamalla seuraavan koodin, jolla annetaan oikeudet ei-sudo käyttäjille kyseiseen root-hakemistoon:

![kuva](https://user-images.githubusercontent.com/105205141/216960155-b5754bd6-cffa-43f1-8953-9f50260a1145.png)

 
 ## b)

 ![kuva](https://user-images.githubusercontent.com/105205141/216955980-ef617bf2-194f-48a0-bf2e-b39a4c97cb34.png)
 
 tein virheen apache2.conf  -tiedostoon poistamalla yhden kaarisulun, joka aiheutti syntaksivirheen. En edes saanut palvelinta takaisin päälle. 
 
 Tämän jälkeen kävin katsomassa error.log:ista jos löytäisin virheilmoitusta asiaan liittyen, mutta sitä ei error.log:iin ollut listattu. Löysin loppujen lopuksi virheen käynnistämällä palvelinta uudelleen, jolloin sain ehdotuksen "You can see the errors by typing this code:"
 
          systemctl status apache2.service

tällä sain seuraavanlaisen virheilmoituksen: 

![kuva](https://user-images.githubusercontent.com/105205141/216958041-cd7284eb-218f-46d3-8352-3dab773f8264.png)

tarkemmin katsoen havaitaan, että on huomattu syntaksivirhe rivillä 80:

 ![kuva](https://user-images.githubusercontent.com/105205141/216958132-b7344cff-2f7b-41e2-9c31-ef9410ecca2d.png)

 avaamalla apache2.conf tiedoston ja menemällä riville 80, löydetään tämä rivi:

![kuva](https://user-images.githubusercontent.com/105205141/216958767-6d56cc32-3261-4015-ae8c-8dd62d785445.png)
 
 josta puuttuu kaarisulku lopusta.

 nyt kun kaarisulku laitetaan takaisin ja käynnistetään palvelin, toimii palvelin ongelmitta. 
