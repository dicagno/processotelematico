# processotelematico
Esempi pratici di interazione con i servizi SOAP del Ministero della Giustizia relativi al Processo Civile Telematico.

##Endpoint dei servizi SOAP
L'endpoint dei servizi SOAP (c.d. proxy) varia a seconda del client che effettua la richiesta:
1. `https://ext.processotelematico.giustizia.it/pda/pycons/$gestore/$registro` nel caso di Software House ed altri soggetti abilitati ad accedere (ad es. professionisti registrati al RegIndE)
2. `https://pda.processotelematico.giustizia.it/$gestore/$registro/backend/rpcrouter` nel caso di PdA (Punti di Accesso) abilitati.

Per `$registro` si intende una stringa composta da:
1. una parte fissa, `GL_`, che sta per "Gestore Locale"
2. una parte variabile (ad es. `MI`) che sta per lo specifico gestore (un elenco dei gestori è disponibile ...qui...)

##Parametri della richiesta
```xml
<value name="parametro0" type="string">VALORE_DEL_PARAMETRO</value>
```
