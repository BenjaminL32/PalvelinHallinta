# Miniprojektien ristiinarviointi  
Tähän ristiinarviontiin valitsin 3 oppilasprojektia sivun https://terokarvinen.com/palvelinten-hallinta/#laksyt kommenttikentästä johon oppilaat olivat lisänneet omia projektejaan  

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

