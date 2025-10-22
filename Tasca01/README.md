# Tasca 01: Gestor de Contrasenyes

## Breu descripció

⚠️ **Alerta!!** EverPia ha estat atacada per ciberdelinqüents.

La consultora on esteu de becaris ha patit una **fuita d’informació (data breach)** i dades confidencials sobre un projecte en desenvolupament estan ara en mans de delinqüents, que amenacen amb fer-les públiques si no es paga un rescat.

Una investigació interna ha revelat que un dels comptes tècnics va ser compromès per l’ús d’una **contrasenya feble o reutilitzada**.

Per això, la **Direcció Tècnica** ha emès una nova directriu:  
🛡️ Tot el personal tècnic ha d’utilitzar un **gestor de contrasenyes validat** per garantir l’ús de credencials **robustes i úniques**.

### El vostre objectiu

Se us encarrega la tasca de **valorar diferents opcions de gestors de contrasenyes** i crear la **documentació necessària per formar l’equip tècnic**.

---

## 🧪 Fase 1: Anàlisi i Justificació (informe.md)

Heu de redactar un **informe tècnic** amb els següents apartats:

### 🔍 Introducció i Justificació

- Explicació del risc de contrasenyes febles o reutilitzades (ex: atac de diccionari, *credential stuffing*).
- Com un **gestor de contrasenyes** ajuda a mitigar aquests riscos.

### ⚖️ Comparativa Tècnica

Realitzeu una **taula comparativa** entre dues eines:

#### 1. Bitwarden (alternativa **online** / núvol)

- Sincronització entre dispositius
- Model de seguretat (*xifratge end-to-end*)
- Facilitat d'accés multiplataforma
- Cost / Model freemium

#### 2. KeePassX / KeePassXC (alternativa **offline** / escriptori)

- Emmagatzematge local d’arxius (.kdbx)
- Independència del núvol
- Codi obert (*open source*)
- Portabilitat de l’arxiu

### ✅ Avantatges i Inconvenients

Resumiu els **pros i contres** de cada eina (online vs offline) des del punt de vista de:

- Seguretat
- Usabilitat
- Continuïtat del negoci

### 📝 Recomanació

Proposeu una eina per a tot el personal tècnic i **justifiqueu tècnicament la vostra elecció**.

---

## 🛠️ Fase 2: Guia d'Ús Tècnica (guia.md)

A partir de l’eina seleccionada a la Fase 1, creeu una **guia pràctica** adreçada a l’equip tècnic. Aquesta guia ha d’incloure:

### 🧩 Instal·lació i Configuració Inicial

- Descàrrega i instal·lació
- Creació del compte mestre o arxiu principal (BBDD)

### 🔐 Generació de Contrasenyes Segures

- Com utilitzar el **generador de contrasenyes** de l’eina
- Configuració de longitud, caràcters especials, etc.

### 📄 Exemples d’Ús i Emplenament Automàtic

- Desar una credencial de correu electrònic
- Desar una credencial d’un servei web o aplicació
- Ús de l’**extensió del navegador** per emplenar automàticament

### 💾 Gestió de Còpies de Seguretat (Backup)

- Com fer una còpia de seguretat de les dades (fitxer `.kdbx` en KeePass o exportació en Bitwarden)
- Recomanacions per **emmagatzemar-la de manera segura** (clau USB xifrada, núvol segur...)

> 🔍 La guia ha de contenir **captres de pantalla** i **explicacions pas a pas clares**.

---

## 📁 Estructura de lliurament

Dins del repositori `projecte-3`, creeu la següent estructura:
