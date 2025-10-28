# 🧩 T03: Gestió flexible de discos (LVM i Espais d’emmagatzematge)

## 📄 Breu descripció

Un cop superada la fase de formació, ja esteu preparats per afrontar el repte dels nostres clients.  
Com ja es va explicar, tenim un **nou i important client: el bufet d’advocats *Garriga i Associats***, un dels més prestigiosos de la ciutat, que ha requerit els serveis de la nostra consultora **Everpia**.

Aquest client gestiona una gran quantitat d'informació **legal sensible**, per la qual cosa la **integritat**, la **disponibilitat (alta redundància)** i la **facilitat de gestió** del seu emmagatzematge són d'importància crítica.

La direcció de *Garriga i Associats* ha expressat la necessitat urgent de **renovar els seus sistemes de servidors** per garantir que la informació estigui protegida contra fallades de disc i que l'espai pugui ser **ampliat sense interrupcions**.

Com a tècnics d’**Everpia**, teniu l'encàrrec de **dissenyar i documentar les solucions d'emmagatzematge** que compleixin aquests requisits tant en **entorns Linux** com **Windows**.  
Aquest disseny permetrà presentar al client una **proposta de solució professional i documentada.**

---

## 🎯 Objectiu principal

Dissenyar i documentar **dues solucions d'emmagatzematge** (una per a servidors **Linux** i una altra per a servidors **Windows**) que compleixin amb els principis de:

- 🔁 **Alta disponibilitat**
- 🧱 **Redundància**
- 📈 **Escalabilitat**

> ⚙️ *Com es tracta d’una prova de concepte, no treballareu amb servidors reals sinó amb màquines virtuals, per facilitar la demostració i documentació dels procediments.*

---

## 🐧 Part 1: Linux — LVM amb Zorin OS

S'utilitzarà la distribució **Zorin OS** (o una alternativa Linux compatible) per demostrar la utilitat del **Logical Volume Manager (LVM)**.

### 🔧 Requisits de la implementació i demostració

#### ⚙️ Configuració inicial
- Crear un **grup de volums (VG)** i un **volum lògic (LV)** utilitzant inicialment un mínim de **dos discs durs simulats de 10 GB** cadascun.
- El volum haurà d’estar **formatat** i **muntat automàticament** al sistema mitjançant l’edició de l’arxiu `/etc/fstab`.

#### 🔁 Alta disponibilitat
- Implementar una configuració de **mirall (lvm_mirror)** que protegeixi la informació davant la fallada d’un disc.

#### 🕒 Instantànies (Snapshots)
1. Afegir **dos discos de 10 GB** addicionals al grup de volums.
2. Crear un volum **`lvm_dades`** amb el primer disc afegit, formatejar-lo i muntar-lo.
3. Afegir-hi alguns fitxers (imatges descarregades d’Internet, per exemple).
4. Usar el **segon disc** per crear un **snapshot (`lv_snapshot`)**.
5. Documentar **com restaurar aquest snapshot** si, per exemple, la informació original es danya.

#### 📈 Escalabilitat
- Demostrar el procés d’**ampliació** del volum utilitzant l’espai lliure restant dins del grup de volums per **augmentar la mida del volum `lv_dades`**.

---

## 🪟 Part 2: Windows — Espais d’emmagatzematge (Storage Spaces)

S'utilitzarà **Windows 11** per demostrar les configuracions possibles mitjançant la tecnologia **Storage Spaces**.

### 🔧 Requisits de la implementació i demostració

#### ⚙️ Configuració inicial
- Crear un **Storage Pool** inicialment amb **tres discos de 10 GB (simulats)**.

#### 🔁 Estudi de configuracions
1. **Resiliència de Mirall (Mirroring)**
   - Utilitzar dos dels discos per crear un espai en **mirall doble**.
   - Comprovar que ofereix **alta disponibilitat** davant la fallada d’un disc.

2. **Mirall triple**
   - Eliminar l’espai anterior i crear-ne un de nou amb **els tres discos** en **mirall triple**.
   - Justificar els **avantatges** respecte al mirroring simple.

3. **Resiliència de Paritat (Parity)**
   - Crear un espai amb **resiliència de paritat**, explicant la seva **eficiència d'espai** en comparació amb el mirall.
   - Afegir tants discos de 10 GB com sigui necessari per completar la configuració.

#### 🧩 Demostració de la gestió
- Mostrar com es **visualitza l'estat dels discos i del pool** des de la **consola de gestió de Windows**, simulant la **facilitat de manteniment** que ofereix aquesta tecnologia.

---

## 👥 Com treballareu i què lliurareu

El treball es farà **en grup** i es dividirà en **dues parts**:

| Equip | Sistema Operatiu | Tecnologia | Objectiu |
|:------|:------------------|:------------|:----------|
| Equip 1 | Linux (Zorin OS) | LVM | Gestió i demostració del sistema LVM |
| Equip 2 | Windows 11 | Storage Spaces | Gestió i demostració dels Espais d’emmagatzematge |

### 📋 Fases del treball

1. **Divisió d’equips**  
   Cada grup treballarà en una de les dues plataformes (Linux o Windows).

2. **Preparació individual**  
   Cada membre elaborarà un **guió de la tasca** amb les comandes, captures i documentació necessària.

3. **Execució en parelles**  
   Cada parella durà a terme la seva part de la **demostració pràctica**.

4. **Revisió i integració**  
   Tot el grup revisarà conjuntament la documentació i la presentació final.

5. **Entrega**  
   Cada membre pujarà la seva versió final al **repositori personal** dins la carpeta `tasca03`.

---

## 📁 Format i estructura de lliurament

La documentació de les dues parts s’ha de fer en **format Markdown**, amb imatges, explicacions i comandes.

Estructura recomanada del projecte:


