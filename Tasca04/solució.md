T04 serveis directori LDAP

![foto](img/carlesLDPA1.jpg)

He hagut de crear els parametres de la màquina desde fora per poder fer la activitat tal i com pertoca.

![foto](img/carlesLDPA2.jpg)

A continuació posarem un adaptador en “xarxa NAT” 

![foto](img/carlesLDPA3.jpg)

I el segon adaptador en amfitrió. 

![foto](img/carlesLDPA4.jpg)

![foto](img/carlesLDPA5.jpg)

Aqui hem hagut de posar el nostre domini que en al meu cas es: “server.innovatech04.test server”

![foto](img/carlesLDPA6.jpg)

Ara amb la comanda “sudo hostnamectl set-hostname server” i despres un “hostname” i un “hostname -f” podem veure si ho hem fet be com s’ens a canviat al domini correctament.

![foto](img/carlesLDPA7.jpg)

Posan aquesta comanda entrem a la configuració de la màquina. 

![foto](img/carlesLDPA8.jpg)

Com a contrasenya posarem usuari i aixi evitarem no oblidar-la.

![foto](img/carlesLDPA9.jpg)

![foto](img/carlesLDPA10.jpg)

Farem una comanda “sudo systemctl status slapd” per veure l’estat ldap que si et surt enable ja esta perfectament l’estat.

![foto](img/carlesLDPA11.jpg)

Farem un “sudo dpkg-reconfigure slapd” per entrar a la configuracio del ldap. 

![foto](img/carlesLDPA12.jpg)

la primera opció posarem que no perque aixi no cancel·lem la configuració de la BDD atés que es al que volem fer.

![foto](img/carlesLDPA13.jpg)

Posem al nom corresponent que en el meu cas es innovatech04.test

![foto](img/carlesLDPA14.jpg)

posem el nom de l’organització que es innovatech04.test

![foto](img/carlesLDPA15.jpg)

I li posem la contrasenya que ens demana la tasca que es “p@ssw0rd”

![foto](img/carlesLDPA16.jpg)

indiquem que quan s’elimini el paquet, també s’esborri la BD creada 


