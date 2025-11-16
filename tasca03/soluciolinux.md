## 🔄 LVM (Linux)

###IMPORTANT: Abans d'iniciar, haurem de crear dos particions de discos dins la màquina virtual en els paramentres

![Imatge](IMGZ/1.png)

Instal·lem el lvm amb la comanda **"sudo apt install lvm2"**

---

![Imatge](IMGZ/2.png)

Per crear els volums físics utilitzaremm la comanda **sudo pvcreate** i crearem dos volums anomenats sdb i sdc

---

![Imatge](IMGZ/3.png)

Amb la comanda **sudo vgcreate** crearem el grup vg_dades per ficar dins els volums **b i c** que hem creat anteriorment

---

![Imatge](IMGZ/4.png)

Per crear el volum lògic amb mirall, el primer que haurem de fer serà crear-lo sense, normal. El crearem amb la comanda **sudo lvcreate**

---

![Imatge](IMGZ/5.png)

Amb la comanda **sudo mkfs.ext4** formatem el volum que hem creat anteriorment

---

![Imatge](IMGZ/6.png)

Escrivim aquesta comanda **"sudo mkdir"** per crear el punt de muntatge

---

![Imatge](IMGZ/7.png)

I després, amb la següent comanda; **sudo mount**, el muntarem

---

![Imatge](IMGZ/8.png)

Amb aquesta comanda el que aconseguim es fer el muntatge automàtic editant ***/etc/fstab***

---

![Imatge](IMGZ/9.png)

![Imatge](IMGZ/10.png)

D'aquesta manera, amb les tres comandes de les fotografies farem la preva que tot estigui correctament

---

![Imatge](IMGZ/11.png)

Apagarem al màquina i en els paràmetres afegirem 2 discos mes. Després, tornem a iniciar la màquina i la terminal

---

![Imatge](IMGZ/12.png)

Afegim els nous discos al VG

---

![Imatge](IMGZ/13.png)

Comprovem que tot està creat correctament i ben organitzat

---

![Imatge](IMGZ/14.png)

![Imatge](IMGZ/15.png)

![Imatge](IMGZ/16.png)

![Imatge](IMGZ/17.png)

Tornem a crear un volum per les noves dades de la mateixa manera que ho hem fet amb la primera part

---

![Imatge](IMGZ/18.png)

Creem l'*snapshot** amb **sudo lvcrate**

---

![Imatge](IMGZ/19.png)

![Imatge](IMGZ/20.png)

![Imatge](IMGZ/21.png)

I restaurem l'*snapshot**

---

![Imatge](IMGZ/22.png)

Per comprovar l'espai lliure en el VG utilitzem **sudo vgdisplay**

---

![Imatge](IMGZ/23.png)

I d'aquesta manera podem ampliar el volum amb **sudo lvextend**

---

![Imatge](IMGZ/24.png)

Redimensionem el sistema de fitxers amb **sudo resize2fs**

---

![Imatge](IMGZ/25.png)

I per últim comprovem que el sistema s'ha redimensionat correctament

---

I amb aixo, la pràctica esta completa
