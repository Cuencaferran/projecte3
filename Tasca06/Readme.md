🧭 T06: Fonaments del Servei DNS
📘 Breu descripció

Com a membres cada cop més integrats de l’equip tècnic de la consultora EverPia, teniu davant un nou repte.
El vostre client, una empresa de màrqueting digital (DigiCore), experimenta de tant en tant errors de connectivitat en certes aplicacions.

L’equip tècnic del client sospita que la causa principal podria ser una resolució de noms (DNS) incorrecta o lenta.
Per aquest motiu, se us ha encarregat realitzar una auditoria teòrica i pràctica del servei DNS, amb l’objectiu de formar el personal del client i oferir eines de diagnosi ràpides i eficients.

🧩 Fase Teòrica: Sessió Formativa

Com a part d’aquesta formació, caldrà elaborar un material formatiu per al personal tècnic de DigiCore.
Els directors tècnics han preparat una sèrie de conceptes clau que cal dominar abans de gravar la píndola formativa (vídeo de 10–15 minuts).

📚 Conceptes a explicar
1. Jerarquia i Estructura del DNS

El DNS té una estructura en arbre jeràrquica:

Root (Arrel)

TLDs (Top-Level Domains) → .com, .org, .cat, .es, etc.

Dominis de segon nivell → tecnocampus.cat, xtec.cat, etc.

Cada nivell delega responsabilitats al nivell inferior.

2. Procés de Resolució

Consulta iterativa: el client demana informació pas a pas a diversos servidors DNS.

Consulta recursiva: el servidor DNS fa totes les cerques per l’usuari i li retorna la resposta final.

Servidor d’arrel (Root Server): primer nivell del sistema DNS, coneix els servidors de TLD.

Servidor autoritatiu: conté la informació real i verificada d’un domini.

3. Tipus de Zones

Zona directa: resol noms a adreces IP.

Zona inversa: resol adreces IP a noms.

Zona primària: conté la còpia original de la base de dades DNS.

Zona secundària: còpia de seguretat sincronitzada amb la primària.

4. Tipus de Registres Clau (Records)
Tipus	Descripció
A	Associa un nom de domini a una adreça IPv4.
CNAME	Defineix un àlies d’un altre domini.
MX	Indica els servidors de correu del domini.
NS	Defineix els servidors de noms autoritatius.
SRV	Especifica serveis disponibles dins d’un domini.
5. Conceptes Essencials

Resposta Autoritativa: indica que el servidor que respon és propietari o responsable del domini.

TTL (Time To Live): temps de validesa d’una resposta DNS a la memòria cau.

Un valor alt redueix trànsit, però propaga canvis més lentament.

Un valor baix actualitza més ràpid, però augmenta el trànsit.

SOA (Start of Authority): registre clau que identifica el servidor principal d’una zona i conté:

Nom del servidor principal.

Correu de l’administrador.

Número de sèrie.

Valors de refresc i caducitat.

6. Reenviadors (Forwarders)

Incondicionals: totes les peticions es reenvien a un servidor DNS concret.

Condicionals: només es reenvien determinades peticions segons el domini.

7. Resolució Local i mDNS

Resolució local: permet la comunicació entre dispositius d’una xarxa sense servidor DNS.

mDNS (Multicast DNS): utilitzat per dispositius com impressores o IoT per anunciar-se automàticament a la xarxa local (.local).

🧪 Fase Pràctica: Diagnosi de Noms (Auditoria amb CLI)

Per demostrar el funcionament real del DNS, caldrà utilitzar eines de diagnosi tant en Linux/macOS com en Windows.

🖥️ Configuració de l’entorn

Equip Zorin OS amb dues interfícies de xarxa:

Primera: NAT.

Segona: adaptador pont.

IP configurada segons les indicacions dels responsables.

🧠 A. Diagnosi Avançada amb dig (Linux / macOS)
Comanda 1: Consulta bàsica de registre A
dig xtec.cat A


Anàlisi:

Identificar la IP de resposta, el valor TTL i el servidor que ha respost.

Comanda 2: Consulta de servidors de noms (NS)
dig tecnocampus.cat NS


Anàlisi:

Determinar quins són els servidors de noms autoritatius del domini.

Comanda 3: Consulta detallada SOA
dig escolapia.cat SOA


Anàlisi:

Identificar el correu de l’administrador i el número de sèrie del domini.

Comanda 4: Consulta de resolució inversa
dig -x 147.83.2.135


Anàlisi:

Observar quin nom de domini està associat a aquesta adreça IP.

💻 B. Comprovació de resolució amb nslookup (Multiplataforma)

L’eina nslookup està disponible a pràcticament tots els sistemes operatius.
Es pot usar amb arguments directes o en mode interactiu, que permet fer diverses consultes.

Comandes bàsiques en mode interactiu:

> set type=A|MX|NS|SOA|TXT|ALL
> server [IP o nom del servidor DNS]
> exit

Comanda 1: Consulta bàsica no autoritativa
> set type=A
> tecnocampus.cat


Anàlisi:

Explicar per què la resposta és no autoritativa (habitualment perquè prové de la memòria cau d’un servidor intermedi).

Comanda 2: Consulta autoritativa
> server [IP del servidor de noms del domini tecnocampus.cat]
> set type=A
> tecnocampus.cat


Anàlisi:

Comparar la resposta amb la de la comanda 1.

Identificar diferències en autoritat, TTL i fonts de dades.

🌐 C. Resolucions Locals

Per últim, s’ha de comprovar el funcionament de la resolució local, especialment útil en xarxes internes sense DNS propi.

Exemples:

Consulta per nom NetBIOS o mDNS (.local).

Verificar la resolució entre equips dins de la mateixa LAN.

📝 Activitat de la Fase Pràctica

Creeu un document anomenat guia.md que inclogui:

Les captures de pantalla de les sis comandes executades.

L’anàlisi i explicació de cada resultat.

Les proves de resolució local i conclusions.

🎯 Objectiu Final

A través d’aquesta activitat, l’equip tècnic de DigiCore serà capaç de:

Comprendre el funcionament intern del DNS.

Diagnosticar incidències de resolució de noms.

Diferenciar respostes autoritatives i no autoritatives.

Millorar la configuració i el rendiment del seu sistema DNS.

🧑‍🏫 Resultat esperat:
Una presentació clara i pràctica dels fonaments del DNS, complementada amb una demostració real d’eines CLI (dig, nslookup) i exemples de resolució local.
