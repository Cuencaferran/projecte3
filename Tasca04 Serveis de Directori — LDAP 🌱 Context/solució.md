# T04 serveis directori LDAP

![foto](img/1cap.jpg)

 He hagut de crear els parametres de la màquina desde fora per poder fer la activitat tal i com pertoca.

 ![foto](img/2cap.jpg)

 A continuació posarem un adaptador en “xarxa NAT” 

![foto](img/3cap.jpg)

I el segon adaptador en amfitrió. 

![foto](img/4cap.jpg)

![foto](img/5cap.jpg)

Aqui hem hagut de posar el nostre domini que en al meu cas es: “server.innovatech04.test server”

![foto](img/6cap.jpg)

Ara amb la comanda “sudo hostnamectl set-hostname server” i despres un “hostname” i un “hostname -f” podem veure si ho hem fet be com s’ens a canviat al domini correctament.

![foto](img/7cap.jpg)

Posan aquesta comanda entrem a la configuració de la màquina. 

![foto](img/8cap.jpg)

Com a contrasenya posarem usuari i aixi evitarem no oblidar-la.

![foto](img/9cap.jpg)

![foto](img/10cap.jpg)

Farem una comanda “sudo systemctl status slapd” per veure l’estat ldap que si et surt enable ja esta perfectament l’estat.

![foto](img/11cap.jpg)

Farem un “sudo dpkg-reconfigure slapd” per entrar a la configuracio del ldap. 

![foto](img/12cap.jpg)

la primera opció posarem que no perque aixi no cancel·lem la configuració de la BDD atés que es al que volem fer.

![foto](img/13cap.jpg)

Posem al nom corresponent que en el meu cas es innovatech04.test

![foto](img/14cap.jpg)

posem el nom de l’organització que es innovatech04.test

![foto](img/15cap.jpg)

I li posem la contrasenya que ens demana la tasca que es “p@ssw0rd”

![foto](img/16cap.jpg)

indiquem que quan s’elimini el paquet, també s’esborri la BD creada 

![foto](img/17cap.jpg)

I li diem que mogui la informació del directori existent a una carpeta de backup.

![foto](img/18cap.jpg)

Aquesta comanda és per entrar a la configuració.

![foto](img/19cap.jpg)

Amb la comanda “sudo nano OU_users.ldif” entre a aquesta configuració on manualment hem hagut de canviar al dn,al ou, posar ObjectClass: Top i ObjectClass: organizationUnit.

![foto](img/20cap.jpg)

Amb la comanda “sudo slapcat” podem comprovar si hem configurat be la configuració i si et surt correctament tot. 

![foto](img/21cap.jpg)

Amb la comanda “sudo apt install ldap-account-manager -y instalarem ldap 

![foto](img/22cap.jpg)

Un cop instalas al ldap, vas al navegador posas la teva ip i t’entrarà aquesta part de la tasca on has de posar una password. 

![foto](img/23cap.jpg)

Seguidament et surtiràn tres opcions li clicarem la opció del mitj que es “edit server profiles”

![foto](img/24cap.jpg)

Seguidament veuras al profile name que s’anomena lam i li posas una contrasenya que t’enrecordis la que he posat jo es “lam”

![foto](img/25cap.jpg)

Un cop possas la contrasenya podras veure totes las configuracions i hem de canviar algunes coses. Las parts que hem de canviar en server settings hem de canviar la part de “list of valid users” que hem de posar el nostre cn=admin, el nostre dc=innovatech04 i el nostre dc=test

![foto](img/26cap.jpg)

Canviem el llenguatge que el posarem en espanyol.

![foto](img/27cap.jpg)

I a tools settings hem de canviar al “tree view” que hem de posar el nostre dc=innovatech04 i el nostre dc=test.

![foto](img/28cap.jpg)

Aqui els tipos de cuentas activas, hem de posar el nostre sufijo LDAP que seria ou=usuari,dc=innovatech04,dc=test

I a la part de grups,ou=grup,dc=innovatech04,dc=test

![foto](img/29cap.jpg)

un cop li donem a save a las configuracions ens demana iniciar sessió, iniciem sessió i et sortirà aquest apartat. Per beure que has canviat correctament els usuaris i els grups. 

![foto](img/30cap.jpg)

com podem veure amb aquesta captura tots els canvis s’han executat correctament. 

![foto](img/31cap.jpg)

Ara un cop aqui dintre crearem primer els nous grups. 

![foto](img/32cap.jpg)

Al nom del primer grup li posarem tech i al numero del GID 10000. I guardem el grup 


![foto](img/33cap.jpg)

I al segon grup ha de dir-se manager i el número GID 10001 i amb al maager i al tech ja tindrem els dos grups que ens demanar creats. 

![foto](img/34cap.jpg)

Un cop creat els grups hem de crear dos usuaris al primer usuari anomenat tech01 i li posem una contrasenya. Sobretot el usuari tech s’ha de posar en el grup que vam crear anomenat tech01. 

![foto](img/35cap.jpg)

I al segon usuari anomenat manager01 i li posem una contrasenya i ja tindrem els dos usuaris sobretot el usuari manager s’ha de posar en el grup creat anteriorment que es al de manager.

![foto](img/36cap.jpg)

Crearem una màquina zorin per conectar al servidor amb el client i que es puguin connectar. 

![foto](img/37cap.jpg)

![foto](img/38cap.jpg)


guardem la configuració, i a la terminal fem un 
sudo hostnamectl set-hostname client 
sudo hostnamectl set-hostname server.innovatech04.test
hostname (que si esta be et sortirà al domini)
hostname -f 

![foto](img/39cap.jpg)

farem un sudo su per entrar al root i fem la comanda dins de la ruta root “apt install libnss-ldap libpam-ldap ldap-utils nscd -y”

![foto](img/40cap.jpg)

Un cop estem aqui dintre posem: ldap:///server.innovatech04.test

![foto](img/41cap.jpg)

Seguidament posem: dc=innovatech04,dc=test

![foto](img/42cap.jpg)

![foto](img/43cap.jpg)

![foto](img/44cap.jpg)

![foto](img/45cap.jpg)

Aqui posem: cn=admin,dc=innovatech04,dc=test

![foto](img/46cap.jpg)

I posem una contrasenya.

![foto](img/47cap.jpg)

Posem aquesta comanda i sobretot sha de posar la contrasenya que vam posar a la primera màquina que era: p@ssw0rd.

![foto](img/48cap.jpg)

![foto](img/49cap.jpg)

Amb la comanda “sudo nano /etc/nsswitch.conf” entre a la configuració i hem de editar al passwd al group al shadow i gshadow posan ldap a totas las parts menys a la gshadow que es queda al files sol. 

![foto](img/50cap.jpg)

![foto](img/51cap.jpg)

Seguidament posem la comanda “sudo nano /etc/pam.d/common-password” On he marcat he hagut de eliminar la linia el terme “use_authtok”.

![foto](img/52cap.jpg)

![foto](img/52cap.jpg)

Aquesta configuració entrem amb la comanda “ sudo nano /etc/pam.d/common-session” i on està en vermell hem hagut d'afegir la línia indicada per crear els perfils. 

![foto](img/53cap.jpg)

Fem aquesta comanda per reinicia al servei.

![foto](img/54cap.jpg)

Et demana la contrasenya de la màquina client la posas i ja hauràs reiniciat al servei. Es tech01 l'usuari i la contrasenya vaig posar 1234.

![foto](img/55cap.jpg)

Seguidament amb la comanda “getent passwd | tail” veiem els usuaris LDAP.

![foto](img/56cap.jpg)

![foto](img/57cap.jpg)

Quan entrem a la configuració, posem:

auth sufficient pam_ldap.so
auth requisite pam_nslogin.so
i afegim una: auth required pam_permit.so

![foto](img/58cap.jpg)

Un cop tot reboot a la màquina. 

![foto](img/59cap.jpg)

I aqui podem entrar amb la màquina client, amb el tech01 i amb el manager01

![foto](img/60cap.jpg)




