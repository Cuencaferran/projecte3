T06: Fonaments del servei DNS

![foto](img_blai/1captura.jpg)


Per començar obrim la terminal, i posem la comanda “dig xtec.cat A” per consultar el registre DNS de tipus A del domini xtec.cat. 

![foto](img_blai/2captura.jpg)

Farem la comanda “ dig tecnocampus.cat NS” per treballar en un entorn de proves segur i aïllat, on es poden fer pràctiques o comprovacions de xarxa (com consultes DNS) sense afectar el sistema real.

![foto](img_blai/3captura.jpg)

farem comanda “ dig escolapia.cat SOA” Per realitzar proves i pràctiques de xarxa en un entorn segur i aïllat, on es poden consultar registres DNS (com el SOA) sense afectar el sistema real.

![foto](img_blai/4captura.jpg)


Farem la comanda “dig -x 147.82.2.135” busca quin nom de domini (hostname) està associat a una adreça IP determinada (en aquest cas,14.82.2.135).

![foto](img_blai/5captura.jpg)

Aquesta comanda serveix per fer una consulta DNS directa per obtenir les adreces IP associades a un nom de domini (en aquest cas, tecnocampus.cat).

![foto](img_blai/6captura.jpg)

farem comanda “nslookup” i posarem set 
type=NS 
Tecnocampus.cat 

per veure els name server dels ns.

![foto](img_blai/7captura.jpg)

mostra informació del servidor DNS per defecte que està utilitzant el teu ordinador o xarxa.

![foto](img_blai/8captura.jpg)

mostra una altra consulta feta amb el comandament nslookup, i en aquest cas s’està consultant el registre A del domini tecnocampus.cat.
