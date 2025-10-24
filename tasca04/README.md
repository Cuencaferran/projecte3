T04: Serveis de Directori. LDAP
Breu descripció

Innovatech, una start-up tecnològica emergent, està experimentant un ràpid creixement i pateix un caos en la gestió dels seus usuaris i accessos.

Actualment, cada servei intern (servidor de fitxers, wiki de documentació, etc.) utilitza la seva pròpia base de dades d’usuaris i contrasenyes i, a més, als ordinadors clients s’usa autenticació local.

Aquesta situació genera diversos problemes crítics:

Problemes detectats

Ineficiència Operativa:
Cada cop que s’incorpora o marxa un empleat, l’equip tècnic ha de crear o eliminar el compte en múltiples sistemes.

Risc de Seguretat:
Els usuaris sovint acaben reutilitzant contrasenyes entre serveis per evitar l’oblit.

Manca d’Escalabilitat:
A mesura que Innovatech afegeix nous serveis, el problema es fa insostenible.

Proposta de Solució

El CEO d’Innovatech ha contactat amb EverPia per tal d’implementar una solució d’autenticació centralitzada.

La solució proposada és utilitzar OpenLDAP (Lightweight Directory Access Protocol), ja que és una solució robusta i de codi obert que s’alinea amb l’esperit d’Innovatech, tenint en compte que tots els ordinadors de l’empresa utilitzen GNU/Linux.

Objectius de la Missió

La vostra missió serà implementar el servei OpenLDAP en un servidor Linux. Això implica:

Instal·lar el servei OpenLDAP.

Configurar el domini base del directori.

Crear la jerarquia d’unitats organitzatives (OU).

Integrar usuaris i grups dins del directori per donar accés a altres serveis de xarxa.

Configurar un equip client perquè utilitzi el directori per autenticar els usuaris.

Documentació de Referència

S’ha redactat un document on s’especifica clarament la feina que s’ha de desenvolupar.
Aquest document està disponible al plec de condicions tècniques (també accessible al Moodle de l’assignatura).

Material de Classe (disponible al Moodle)

UD04.AA1: Serveis de Directori

UD04.AA2: Instal·lació OpenLDAP

UD04.AA3: Configuració del Directori

UD04.AA5: Afegir un Client al Directori
