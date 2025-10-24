# **T01: Gestor de contrasenyes**

**Introducció:** 

Les contrasenyes febles o reutilitzades són un risc crític per a la seguretat de l'empresa, ja que poden ser explotades mitjançant atacs com el de diccionari o credential stuffing. Aquest tipus de vulnerabilitats permet als ciberdelinqüents accedir fàcilment a sistemes i dades sensibles, amb greus conseqüències per a la privacitat i la reputació corporativa. Per mitigar aquest risc, és essencial adoptar un gestor de contrasenyes, que ajudi a generar, emmagatzemar i gestionar contrasenyes úniques i robustes per a cada servei. Un gestor de contrasenyes adequat pot evitar la reutilització de credencials i garantir una seguretat molt més alta en el maneig de la informació.

**Comparativa tècnica: bitwarden vs KeePassXC**

| Característica | Bitwarden (online/nuvol) | KeepassXC (online/escriptori) |
| :---- | :---- | :---- |
| Sincronització | Sincronització automàtica en el núvol entre dispositius. | No té sincronització automàtica (necessita gestió manual). |
| Seguretat | Xifratge End-to-End i emmagatzematge al núvol. | Emmagatzematge local (fitxer KDBX), xifratge fort. |
| Accés des de múltiples dispositius | Accessible des de qualsevol dispositiu amb connexió a internet. Inclou aplicacions per a mòbils i navegadors. | Només accessible des del dispositiu on es desi el fitxer local, a no ser que es sincronitzi manualment. |
| Model de Cost | Pla freemium: versió gratuïta amb funcionalitats bàsiques, i versió Premium amb característiques avançades. | Totalment gratuït i open-source. No requereix subscripcions. |
| Facilitat d'Ús | Molt fàcil d'usar amb una interfície intuïtiva i integració amb els navegadors. | Una mica més complex d'usar, especialment per a usuaris no tècnics. |
| Portabilitat | Completament dependent d'internet per la sincronització, però permet accedir des de qualsevol lloc. | Totalment portàtil si es desar el fitxer KDBX a una unitat externa o dispositiu. |
| Privacitat | Compta amb una política de privacitat sòlida, tot i que implica confiar en el proveïdor del núvol. | 100% privat ja que el fitxer es desa localment i no es depèn de tercers. |
| Còpia de seguretat i recuperació | Automàtica, basada en el núvol. | Manual, desar còpies de seguretat del fitxer KDBX en dispositius segurs (USB, núvol xifrat, etc.). |

#### **Avantatges i Inconvenients**

**Bitwarden:**

**Avantatges:**

**Facilitat d'ús**: Configuració senzilla i accessible des de diversos dispositius.

**Accés remot**: La sincronització entre dispositius facilita l'accés constant.

**Seguretat alta**: Xifratge **end-to-end** que garanteix que ni els administradors del servei poden accedir a les contrasenyes.

**Model freemium**: La versió gratuïta cobreix les necessitats bàsiques i la versió Premium aporta funcionalitats addicionals.

**Inconvenients:**

**Dependència del núvol**: Si hi ha una fallada del servei en el núvol, podria dificultar l'accés a les contrasenyes (tot i que el xifratge end-to-end minimitza el risc).

**Dependència d'internet**: No podrà utilitzar-se sense connexió, excepte a través d'alguns mecanismes com el mode offline en la versió mòbil.

**KeePassXC:**

**Avantatges:**

**Privacitat total:** El fitxer KDBX es desa localment i no depèn d'un tercer per emmagatzemar les contrasenyes.

**Control total**: L'usuari controla completament l'emmagatzematge i la còpia de seguretat.

**Gratuït i open-source**: No té cap cost i és molt flexible pel que fa a personalització.

**Inconvenients:**

**Manca de sincronització automàtica**: Requereix una gestió manual de còpies de seguretat o sincronització entre dispositius.

**Menys accessible**: El fitxer només es pot obrir en el dispositiu on es troba, a menys que s'utilitzi una solució manual per sincronitzar-lo entre dispositius.

**Interfície menys intuïtiva**: Pot resultar menys amigable per a usuaris no tècnics.

**Recomanació:** 

Després de l'anàlisi, es recomana Bitwarden com a solució per a la gestió de contrasenyes del personal tècnic de l'empresa. Els principals arguments són la facilitat d'ús, la seguretat robusta amb xifratge end-to-end, i la capacitat de sincronització automàtica entre dispositius, la qual cosa permet una gestió de contrasenyes més flexible i segura, especialment en un entorn laboral que requereix constant mobilitat. Tot i que KeePassXC és una bona opció per a aquells que prioritzin la privacitat total i l'ús offline, la necessitat de garantir un accés constant i segur des de diversos dispositius fa que Bitwarden sigui la millor opció per al personal tècnic de l'empresa.

1
