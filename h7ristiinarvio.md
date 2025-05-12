# Miniprojektien ristiinarviointi  
Tähän ristiinarviontiin valitsin 3 oppilasprojektia sivun https://terokarvinen.com/palvelinten-hallinta/#laksyt kommenttikentästä johon oppilaat olivat lisänneet omia projektejaan. Otin myös projekteja Tero Karvisen Laksu-palvelusta

## Ensimmäinen projekti - https://github.com/nurminenkasper/netris-salt-vagrant-module
Ensimmäiseksi valitutui Kasper Nurmisen tekemä projekti, jolla saltilla asennetaan Netris niminen peli minion tietokoneeseen saltilla.  
Lähdin eteenpäin ensimmäisestä vaiheesta, eli loin uuden tiedoston ja kopion github repon sinne komennolla ``    git clone https://github.com/nurminenkasper/netris-salt-vagrant-module.git``  
Tämän jälkeen navigoin ladatun modulin sisään ja annoin komennon ``vagrant up``  
<img width="713" alt="image" src="https://github.com/user-attachments/assets/489f9bb0-5719-4844-800d-d8c2a7d57ac6" />  
Vagrantin ajo meni onnistuneesti läpi noin 4 minuutissa. Nyt annaan ohjeissa seuraavaksi olevan vaiheen, eli otan ssh yhteyden masteriin, hyväksyn avaimet ja ajan saltin konfiguraatiotiedoston.  
<img width="527" alt="image" src="https://github.com/user-attachments/assets/ac7126f2-9bc4-401c-be4a-dbf3630f5d51" />  
Niinkuin yllä olevasta kuvasta näkee, salt komennon ``sudo salt '*' state.apply netris`` meni onnistuneesti läpi ja kaikki on nyt valmiina viimeistä testiä varten.  
Annan ohjeistuksessa olevan komennon ``ssh vagrant@192.168.88.102 -p 2222`` terminaaliin ja katson toimiiko peli.  
<img width="619" alt="image" src="https://github.com/user-attachments/assets/7fc96c6a-5441-4566-9849-031faf52abf1" />  
Hurraa, peli lähti toimimaan. 
Ohjeet olivat äärimmäisen helpot seurata, ja konifguraatiossa asiat oltiin tehty siten oikein, että minulle jäi hyvin vähän itse tehtävää että sain projektin toimimaan.
## Toinen projekti - https://github.com/thsoini/Projekti/blob/main/monitori-salstack.md
Toiseksi projektiksi valikoitus "thsoini"-nimimerkin tekemä projekti monitorointipinon asennuksesta saltilla.
Valitettavasti raportilla ei ollut tietoa siitä millä tavalla vagrantfilen kuuluisi olla konfiguroitu tai saltin asennukseta ei ollut mitään dokumentaatiota.  
Tämä teki raportin seuraamisesta huomattavan hankalaa.  
Projekti on ilmiselvästi tehty käyttäen laajaa kurssin ulkopuolista ymmärrystä ja harrastuneisuutta, joten tässä ehkä tehdään myös hieman oletuksia raporttia lukevan kyvykkyydestä.  
Myöskin muutamat kuvakaappaukset etenemisvaiheita ovat ilmeisesti mennyt rikki, niin en tiedä saanko toistettua tuloksia, mutta kokeillaan.  
Aloitin perustamlla uuden kansion ja ajamalla ``vagrant init debian/bookworm64`` komennolla uuden vagrantfilen sisään, jonka jälkeen nostin virtuaalitietokoneen ylös ``vagrant up`` komennolla.  
Tämän jälkeen otin yhteyden tietokoneeseen ``vagrant ssh default`` komennolla. Oletan että projektissa ajetaan salt komentoja lokaalisti, joten asennan tähän koneeseen salt-minionin.
Asensin salt-minionin asentamalla salt paketit saltprojektin nettisivuilta ja asensin salt-minionin.  
Nyt aloitetaan itse projektin toteutus, aloitan luomalla kansiopolun ohjeiden mukaan komennolla ``sudo mkdir -p /srv/salt/monitoring/files``  
Luon sinne myös tiedoton top.sls komennolla ``sudo nano top.sls`` jonka sisällön kaivan raportilta.  
<img width="461" alt="image" src="https://github.com/user-attachments/assets/9c865dab-9804-4dec-9b04-66fd1a1a947a" />  
Nyt kun ne on ajettu, luon samaan kansioon promethus.yml tiedoston komennolla ``sudo nano prometheus.yml`` jonka sisällön otan myös raportilta.  
<img width="529" alt="image" src="https://github.com/user-attachments/assets/04ebe0d6-a3dc-4ecd-9133-b0a929f2139d" />  
Ja viimeisenä valmisteluna luon ohjeiden mukaisesti init.sls tiedoston komennolla ``sudo nano init.sls`` sisältö myös raportista.  
<img width="470" alt="image" src="https://github.com/user-attachments/assets/430b13cc-9287-4ca1-97d8-2e8d4209b6c7" />  
Nyt kun nämä vaiheet on suoritettu, on aika ajaa init.sls tiedosto. Koska ajan tätä lokaalisti, muutin projektin dokumentaatiossa olevan komennon muotoon ``sudo salt-call --local -l info state.apply init``  
<img width="670" alt="image" src="https://github.com/user-attachments/assets/18cf62c1-9e47-4fc7-9fa9-d7eff1ea5f1b" />  
Valitettavasti en saanut projektia toteutettua koneellani, aikaa tämän ongelma ratkaisemiseksi ei valitettavasti ollut.
## Kolmas projekti - https://github.com/JesseTuomi/character_sheet/tree/main  
Kolmanneksi projektiksi valikoitus Jesse Tuomen projekti hahmolomakkeen luomisesta tabletop-RPG peleihin käyttäen saltia.  
Koitan saada projektin ajettua nyt omalla laittellani.  
Aloitan ohjeiden mukaisesti kloonaamalla repon githubista luomaani testitiedostoon.  
<img width="611" alt="image" src="https://github.com/user-attachments/assets/b79af161-45b0-45d7-984b-55612deb81fd" />  
Nähtävsti repon kloonaaminen githubista ei toimi, näköhään tuohon urliin on jäänyt "yourusername"- placeholder. Myöskään projektin hakeimistorakenne ei sovellu projektin kloonaamiseen suoraan. En myöskään valitettavasti ymmärrä projektin dokumentaatiosta tarpeeksi että mihin mikäkin tiedosto menee ja mikä skripti kuuluu minnekkin.  
Projektin luonne on hyvin mielenkiintoinen ja itsekin roolipelien pelaajana olisin kovin halunnut saada tuon ajettua :(  
Jos projektin olisi saanut ladattua kloonaamalla kansiorakenteen olisi saanut ladattua kloonaamalla githubista, olisi tämä ollut huomattavasti helpompaa
  







  



