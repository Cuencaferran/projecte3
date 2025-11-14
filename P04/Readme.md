# 🧩 Producte 04 – Publicació de la Configuració DNS a GitHub

Molt benvinguts a la vostra nova tasca, consultors! 🖐️  
Com a membres de l'equip de sistemes d’**EverPia**, ja heu configurat un servidor DNS com a prova de concepte per al client **Digicore**. Actualment, aquesta configuració es troba dins d’una màquina virtual, però el nostre objectiu és **publicar-la a GitHub** per garantir que es pugui replicar fàcilment sense partir de zero.

L’objectiu final és que qualsevol tècnic pugui descarregar els arxius al servidor Linux i reiniciar el servei per obtenir un **servidor DNS funcional** ✅.

---

# 🚀 Fase 1: Preparació de la Connectivitat i Extracció dels Arxius

## 🔌 Pas 1.1 – Configuració de la Interfície Host-Only

Per poder copiar els fitxers de la màquina virtual Ubuntu Server al vostre PC host, cal assegurar la connectivitat via Host-Only.

1. Afegiu una **segona interfície de xarxa** a la màquina virtual i configureu-la com a **Host-Only**.  
2. Activeu-la i comproveu la connectivitat des del vostre PC físic (ping, IP correcta, etc.) ✅.

---

## 🔐 Pas 1.2 – Còpia Segura de Fitxers amb SCP

Un cop hi ha connectivitat, utilitzareu **SCP (Secure Copy Protocol)** per transferir els fitxers al vostre ordinador.

### 📁 Fitxers a copiar:

/etc/bind/named.conf.options
/etc/bind/named.conf.local
Tots els arxius de zones dins:  
  /etc/bind/zones/

### 💻 Exemple de comanda SCP:
bash

scp usuari@IP-de-la-MV:/etc/bind/named.conf.options .

