# Tasca 04: Serveis de Directori — LDAP 🌱 Context

## 🏢 Cas Pràctic: El repte d'Innovatech

**Innovatech**, una start-up tecnològica emergent, està experimentant un ràpid creixement i pateix un caos en la gestió dels seus usuaris i accessos. 

Actualment, cada servei intern (servidor de fitxers, wiki de documentació, etc.) utilitza la seva pròpia base de dades d'usuaris i contrasenyes i, a més, als ordinadors clients s'usa autentificació local. Això genera diversos problemes crítics:

* **Ineficiència Operativa:** Cada cop que s'incorpora o marxa un empleat, l'equip tècnic ha de crear o eliminar el compte en múltiples sistemes.
* **Risc de Seguretat:** Els usuaris sovint acaben reutilitzant contrasenyes entre serveis per evitar l'oblit.
* **Manca d'Escalabilitat:** A mesura que Innovatech afegeix nous serveis, el problema es fa insostenible.

---

## 🎯 Missió del Projecte

El CEO d’Innovatech ha contactat amb **EverPia** per tal d’implementar una solució d’autenticació centralitzada. La solució proposada és utilitzar **OpenLDAP** (*Lightweight Directory Access Protocol*), ja que és una eina robusta, escalable i de codi obert que s’alinea perfectament amb l’esperit d’Innovatech (on tots els ordinadors de l’empresa utilitzen distribucions **GNU/Linux**).

La vostra missió com a equip tècnic serà **implementar el servei OpenLDAP en un servidor Linux**. Això implica:
1. **Instal·lar** el servei OpenLDAP i les seves eines de gestió.
2. **Configurar** el domini base de l'empresa.
3. **Dissenyar i crear** la jerarquia d'Unitats Organitzatives (`OU`).
4. **Integrar** els usuaris i grups inicials que posteriorment s'utilitzaran per donar accés a altres serveis de xarxa.
5. **Configurar un equip client** per tal que validi l'autenticació directament contra el directori centralitzat.

> 📄 **Nota:** Trobareu les especificacions detallades de la feina a desenvolupar en el **plec de condicions tècniques** disponible al Moodle de l’assignatura.

---

## 📚 Material de Referència i Suport

Per realitzar correctament aquesta tasca, disposeu del següent material didàctic a la plataforma Moodle:

* 📁 **UD04.AA1** Serveis de Directori (Conceptes teòrics bàsics)
* 📁 **UD04.AA2** Instal·lació OpenLDAP
* 📁 **UD04.AA3** Configuració del directori (Fitxers `.ldif` i estructura)
* 📁 **UD04.AA5** Agregar client al directori (Configuració de PAM / NSS)

---

## 🛠️ Estructura de lliurament recomanada

Si utilitzeu aquesta carpeta per pujar la vostra documentació, es recomana adjuntar:
* `[Codi/LDIF]` Fitxers de configuració o càrrega d'usuaris generats.
* `[Documentacio]` Memòria tècnica o captures de pantalla que demostrin el correcte funcionament de l'autenticació del client.