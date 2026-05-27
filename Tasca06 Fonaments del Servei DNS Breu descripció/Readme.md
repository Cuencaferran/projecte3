# Tasca 06: Fonaments del Servei DNS — Breu descripció 🌐

## 🏢 Cas Pràctic: L'auditoria per a DigiCore

Com a membres de l'equip tècnic de la consultora **EverPia**, ens enfrontem a un nou repte. El nostre client, **DigiCore** (una empresa de màrqueting digital), està experimentant errors intermitents de connectivitat en certes aplicacions. L'equip tècnic sospita que la causa principal és una resolució de noms (DNS) incorrecta o lenta.

La nostra missió és realitzar una **auditoria teòrica i pràctica** del servei DNS per tal de formar el personal del client i oferir-los eines de diagnosi ràpides.

---

## 📚 Fase Teòrica: Sessió Formativa i Píndola de Vídeo

Per assegurar la màxima qualitat, hem d'elaborar material formatiu que cobreixi els següents conceptes clau:

<details>
<summary>🔍 Prem aquí per veure els conceptes teòrics clau a dominar</summary>

* **Jerarquia i Estructura:** Estructura en arbre del DNS (`Root` > `TLDs` > `Segon Nivell`).
* **Procés de Resolució:** Diferències entre consultes iteratives i recursives. Concepte de *Root Server* i Servidor Autoritatiu.
* **Tipus de Zones:** Zona directa i inversa; zona primària i zona secundària.
* **Tipus de Registres Clau (Records):** Funció de `A`, `CNAME`, `MX`, `NS` i `SRV`.
* **Conceptes Essencials:**
    * *Resposta Autoritativa:* Què significa i com identificar-la.
    * *Time To Live (TTL):* Funció i impacte en la propagació i rendiment.
    * *Start of Authority (SOA):* Informació crítica que conté i per què és vital.
    * *Reenviadors:* Condicionals i incondicionals.
    * *Resolució Local:* Mecanismes sense servidor entre clients (protocol **mDNS**).
</details>

### 🎬 Activitat Teòrica
Preparació d'una píndola formativa en **vídeo (d'entre 10 i 15 minuts)** on s'expliquin de forma breu, clara i didàctica tots aquests conceptes per al personal de DigiCore.

---

## 🛠️ Fase Pràctica: Diagnosi de Noms (Auditoria amb CLI)

Demostració de l'ús de les principals utilitats de diagnosi DNS en els sistemes de l'empresa (Linux/macOS i Windows). 

*🖥️ **Entorn de proves:** Equip Zorin OS amb dues interfícies: una en **NAT** i la segona en **adaptador pont** (IP configurada segons les indicacions dels responsables).*

### 🎯 Quadre de Comandes d'Auditoria

| Mètode / Eina | Objectiu de la Prova | Comanda a Executar |
| :--- | :--- | :--- |
| **A. Avançada (`dig`)** | Consulta Bàsica de Registre A | `dig xtec.cat A` |
| **A. Avançada (`dig`)** | Consulta de Servidors de Noms (NS) | `dig tecnocampus.cat NS` |
| **A. Avançada (`dig`)** | Consulta Detallada SOA | `dig escolapia.cat SOA` |
| **A. Avançada (`dig`)** | Consulta de Resolució Inversa | `dig -x 147.83.2.135` |
| **B. Multiplataforma (`nslookup`)** | Consulta Bàsica no Autoritativa | `nslookup` (mode interactiu) <br> `> set type=A` <br> `> tecnocampus.cat` |
| **B. Multiplataforma (`nslookup`)** | Consultes Autoritatives directes | `> server [IP_Servidor_NS]` <br> `> set type=A` <br> `> tecnocampus.cat` |

### 🏠 Resolucions Locals
Comprovació del funcionament de la resolució local en entorns de xarxa local on no es disposa de servidor de noms propi (evitant l'ús directe de les IPs gràcies a **mDNS**).

---

## 📋 Entregable d'aquesta carpeta

* **`guia.md`**: Document guia amb els resultats, anàlisis i conclusions estructurades.
* 📸 **Captures de pantalla**: S'han d'incloure les captures de les **6 comandes anteriors** provades a l'entorn de terminals, juntament amb les proves de resolució local.