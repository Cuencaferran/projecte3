# 📊 P05: Presentació sistemes emmagatzematge – LVM vs Storage Spaces

## 📌 Descripció del producte

En el camí per arribar a ser consultors d’infraestructura sènior, s’ha assignat una tasca de màxima prioritat per a un client: una empresa de disseny que necessita modernitzar els seus servidors de fitxers.

La missió és **preparar i defensar una presentació comparativa exhaustiva** davant el client, per educar la direcció i els tècnics sobre dues tecnologies líders per a la infraestructura de servidors de fitxers:

- **LVM (Logical Volume Manager)** – Solució estàndard per a la gestió dinàmica d’emmagatzematge en entorns Linux.
- **Storage Spaces** – Eina nativa de Microsoft per a la virtualització d’emmagatzematge en servidors Windows.

La presentació ha de ser clara, tècnica però accessible, i ha de justificar l’elecció tecnològica per tal d’aconseguir l’aprovació del pressupost per a la implementació dels nous servidors de fitxers.

## 🎯 Objectius específics

- Realitzar material professional per a presentacions orals.
- Desenvolupar habilitats de comunicació tècnica davant d’un client.
- Comparar objectivament LVM i Storage Spaces.
- Educar el client sobre els avantatges i implicacions de cada tecnologia.
- Justificar la recomanació final basant-se en l’entorn i necessitats del client.

## 🧩 Contingut de la presentació

La presentació s’estructura en els blocs següents (durada estimada: 10-15 minuts):

### 1. Context del client i necessitats del projecte
- Empresa de disseny: volum de fitxers grans (multimèdia, projectes), necessitat d’escalabilitat, fiabilitat i rendiment.
- Requisits principals: gestió dinàmica de l’espai, tolerància a fallades, cost controlat, facilitat d’administració.

### 2. Introducció a les dues tecnologies
- **LVM**: capa de gestió lògica sobre discs físics, permet redimensionar volums, crear snapshots, etc.
- **Storage Spaces**: virtualització d’emmagatzematge a Windows Server, agrupa discs en un pool i crea espais d’emmagatzematge amb diferents nivells de redundància.

### 3. Terminologia equivalent

| LVM | Storage Spaces |
|-----|----------------|
| Disc físic (PV) | Disc físic |
| Grup de volums (VG) | Storage pool |
| Volum lògic (LV) | Virtual disk / Space |
| Extent físic/lògic | Slab / interleave |
| Snapshot (LVM2) | Shadow copy / snapshots |

### 4. Semblances i diferències

| Aspecte | LVM | Storage Spaces |
|---------|-----|----------------|
| **Plataforma** | Linux | Windows Server |
| **Redimensionament en calent** | Sí | Sí (fins a cert límit) |
| **Redundància** | Per RAID subjacent o per mirror amb LVM (RAID1) | Nativa: mirror, parity, simple |
| **Màxims** | 255 PV per VG, 255 LV, mida LV fins a 16 EB (teòric) | 64 PB per pool, 5 PB per disc virtual (Windows Server 2019) |
| **Rendiment** | Molt bo, amb opcions de striping | Bo, però depèn de la capa de redundància |
| **Cost** | Gratuït (Open Source) | Inclòs en Windows Server (cost de llicència) |
| **Eines de gestió** | CLI (`pvcreate`, `vgcreate`, `lvcreate`) | GUI (Administrador de servidor) + PowerShell |

### 5. Avantatges per al servidor de fitxers del client

#### Avantatges de LVM
- Flexibilitat màxima: redimensionar volums sense aturar el servei.
- Snapshots per a còpies de seguretat consistents.
- Gratuït i sense costos addicionals.
- Gran maduresa i documentació.

#### Avantatges de Storage Spaces
- Integració nativa amb Windows (fàcil per a equips acostumats a entorns Microsoft).
- Redundància integrada (mirror, parity) sense necessitat de RAID maquinari.
- Suport per a diferents tipus de discs (HDD, SSD, NVMe) i capes d’emmagatzematge (*tiering*).
- Creació des de la interfície gràfica, reduint corba d’aprenentatge.

### 6. Justificació de la proposta (recomanació)

Segons el perfil del client (empresa de disseny, probablement amb equips Windows i pocs administradors Linux), la **recomanació és Storage Spaces** per:
- Menor fricció amb l’entorn existent.
- Redundància integrada (especialment mirror) que protegeix els fitxers de disseny.
- Facilitat d’administració per a tècnics no especialitzats en Linux.
Si el client té un equip tècnic amb experiència Linux i vol reduir costos de llicència, LVM seria una alternativa viable.

### 7. Conclusió i següents passos
- Resum de la comparativa.
- Pressupost estimatiu (cost de llicència Windows Server si cal).
- Proposta d’implementació pilot.

## 📎 Format i requisits de la presentació

| Element | Detall |
|---------|--------|
| **Durada** | 10-15 minuts (preguntes incloses) |
| **Suport visual** | PowerPoint, Google Slides o Canva |
| **Participació** | Tots els membres del grup han d’intervenir |
| **Material complementari** | Taula comparativa imprimible (handout) |

## 📂 Lliurables associats

- Fitxer de la presentació (PDF o enllaç a Google Slides).
- Aquest README (documentació del producte P05 dins del portfoli).
- (Opcional) Guió de l’exposició.

## ✅ Compliment dels objectius

| Objectiu | Estat |
|----------|-------|
| Presentar característiques principals de LVM i Storage Spaces | ✅ |
| Establir terminologia equivalent | ✅ |
| Analitzar semblances i diferències (escalabilitat, rendiment, cost) | ✅ |
| Exposar avantatges per a servidors de fitxers | ✅ |
| Justificar la recomanació segons les necessitats del client | ✅ |
| Realitzar material de presentació professional | ✅ |

## 🔗 Enllaç a la presentació (exemple)

> **[Presentació: LVM vs Storage Spaces per al client de disseny](https://docs.google.com/presentation/d/...)**  

---
