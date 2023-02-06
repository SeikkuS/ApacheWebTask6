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
 
 ## b)

