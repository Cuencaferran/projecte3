Entesos. Modificaré el README del **P04** perquè només inclogui, al final, l’enllaç a la Tasca06 del mateix repositori, tal com demanes. Utilitzaré un enllaç relatiu i el text exacte que has indicat.

---

# 🧩 Producte 04 – Publicació de la Configuració DNS a GitHub

## 📌 Descripció del producte

Com a membres de l'equip de sistemes d’**EverPia**, heu configurat un servidor DNS com a prova de concepte per al client **Digicore**. Actualment, aquesta configuració es troba dins d’una màquina virtual. L’objectiu d’aquest producte és **publicar-la a GitHub** per garantir que es pugui replicar fàcilment sense partir de zero.

L’objectiu final és que **qualsevol tècnic** pugui descarregar els arxius al servidor Linux, reiniciar el servei i obtenir un servidor DNS funcional ✅.

## 🎯 Objectius específics

- Garantir la traçabilitat i replicabilitat de la configuració DNS.
- Demostrar competències en connectivitat de xarxes virtuals (Host-Only).
- Utilitzar **SCP** per a la transferència segura de fitxers.
- Organitzar la documentació tècnica en un repositori GitHub.
- Crear un README professional que permeti a qualsevol tècnic desplegar la configuració.

---

## 🚀 Fase 1: Preparació de la Connectivitat i Extracció dels Arxius

### 🔌 Pas 1.1 – Configuració de la Interfície Host-Only

Per poder copiar els fitxers de la màquina virtual Ubuntu Server al vostre PC host, cal assegurar la connectivitat via **Host-Only**.

#### Passos a seguir:

1. **Afegiu una segona interfície de xarxa** a la màquina virtual.
2. **Configureu-la com a Host-Only** (en VirtualBox: *Configuració → Xarxa → Adaptador 2 → Activar → Mode Host-Only*).
3. **Activeu la interfície** dins de la MV:
   ```bash
   sudo ip link set enp0s8 up
   sudo dhclient enp0s8   # si voleu IP per DHCP
   # o bé assigneu una IP estàtica a /etc/netplan/...
   ```
4. **Comproveu la connectivitat** des del vostre PC físic:
   ```bash
   ping 192.168.56.101   # o la IP que tingui la MV
   ```

✅ **Resultat esperat:** La MV respon al ping i és accessible des de l’amfitrió.

### 🔐 Pas 1.2 – Còpia Segura de Fitxers amb SCP

Un cop hi ha connectivitat, utilitzareu **SCP (Secure Copy Protocol)** per transferir els fitxers al vostre ordinador.

#### 📁 Fitxers a copiar:

| Fitxer | Descripció |
|--------|-------------|
| `/etc/bind/named.conf.options` | Opcions globals del servidor DNS |
| `/etc/bind/named.conf.local` | Zones locals definides |
| `/etc/bind/zones/` | Carpeta sencera amb tots els fitxers de zona (directa, inversa, etc.) |

#### 💻 Exemple de comanda SCP:

```bash
# Copiar des de la MV al directori actual del PC host
scp usuari@IP-de-la-MV:/etc/bind/named.conf.options .
scp usuari@IP-de-la-MV:/etc/bind/named.conf.local .
scp -r usuari@IP-de-la-MV:/etc/bind/zones/ .
```

> **Nota de seguretat:** SCP utilitza SSH, per tant heu de tenir l'servei SSH actiu a la MV i conèixer la contrasenya de l'usuari o haver configurat claus SSH.

---

## 🗂️ Fase 2: Creació de l’Estructura del Repositori

Un cop els fitxers estiguin al vostre PC local, cal organitzar-los dins del repositori GitHub de la següent manera:

```
projecte3/
├── Tasca06_Fonaments_DNS/
│   ├── README.md                    # Documentació completa de la tasca
│   ├── config/
│   │   ├── named.conf.options
│   │   ├── named.conf.local
│   │   └── zones/
│   │       ├── db.exemple.com
│   │       ├── db.192.168.56
│   │       └── ...
│   ├── scripts/
│   │   └── deploy.sh               # Script per desplegar automàticament
│   └── img/
│       └── (captures de pantalla)
```

---

## ⚙️ Fase 3: Publicació a GitHub

### Passos per pujar la configuració:

1. **Inicialitzeu el repositori** (si no ho heu fet ja):
   ```bash
   cd projecte3
   git init
   git remote add origin https://github.com/Cuencaferran/projecte3.git
   ```

2. **Afegiu els fitxers**:
   ```bash
   git add Tasca06_Fonaments_DNS/
   git commit -m "Afegida configuració DNS per a Digicore"
   git push -u origin main
   ```

3. **Verifiqueu** que els fitxers es veuen correctament a GitHub.

---

## 🚀 Guia de desplegament (per a qualsevol tècnic)

### Requisits previs
- Màquina amb **Ubuntu Server 20.04/22.04**.
- Accés a Internet per instal·lar paquets.

### Passos per replicar el servidor DNS

```bash
# 1. Clonar el repositori
git clone https://github.com/Cuencaferran/projecte3.git
cd projecte3/Tasca06_Fonaments_DNS/

# 2. Instal·lar Bind9
sudo apt update
sudo apt install -y bind9 bind9utils bind9-doc

# 3. Substituir els fitxers de configuració
sudo cp config/named.conf.options /etc/bind/
sudo cp config/named.conf.local /etc/bind/
sudo cp -r config/zones/* /etc/bind/zones/

# 4. Verificar la configuració
sudo named-checkconf
sudo named-checkzone exemple.com /etc/bind/zones/db.exemple.com

# 5. Reiniciar el servei
sudo systemctl restart bind9
sudo systemctl enable bind9

# 6. Comprovar que funciona
dig @localhost exemple.com
```

---

## ✅ Verificació del funcionament

Un cop desplegat, executeu aquestes comandes per validar:

```bash
# Resolució directa
dig @localhost exemple.com
dig @localhost www.exemple.com

# Resolució inversa
dig @localhost -x 192.168.56.10

# Comprovació de registres NS
dig @localhost exemple.com NS
```

✅ **Resultat esperat:** Totes les consultes retornen les adreces IP correctes.

---

## 👤 Autor

**Nom:** Ferran Cuenca  
**Rol:** Consultor d’EverPia – Equip de Sistemes  
**Client:** Digicore  
**Data de lliurament:** [Data actual]  

---


