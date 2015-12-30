L'esempio sottoindicato rappresenta una invocazione del metodo SOAP `getServiceNames`.

##Endpoint dei servizi SOAP
L'endpoint dei servizi SOAP (c.d. proxy) varia a seconda del client che effettua la richiesta:
1. `https://ext.processotelematico.giustizia.it/pda/pycons/$gestore/$registro` nel caso di Software House ed altri soggetti abilitati ad accedere (ad es. professionisti registrati al RegIndE)
2. `https://pda.processotelematico.giustizia.it/$gestore/$registro/backend/rpcrouter` nel caso di PdA (Punti di Accesso) abilitati.

Per `$registro` si intende una stringa composta da:
1. una parte fissa, `GL_`, che sta per "Gestore Locale"
2. una parte variabile (ad es. `MI`) che sta per lo specifico gestore (un elenco dei gestori è disponibile ...qui...)

##Richiesta SOAP
```xml
<?xml version='1.0' encoding='UTF-8'?>
<soap-env:Envelope
    xmlns:soap-env="http://schemas.xmlsoap.org/soap/envelope/">
    <soap-env:Header>
        <ws:invocationDomain
            xmlns:ws="http://www.netserv.it/anag/security"
            soap-env:MustUnderstand="true"
            group="jpwusers"
            role="JPW"
            name="JPW">
        </ws:invocationDomain>
    </soap-env:Header>
    <soap-env:Body>
        <m:getServiceNames
            xmlns:m="urn:CONS-SICC-BE">
        </m:getServiceNames>
    </soap-env:Body>
</soap-env:Envelope>
```

##Risposta SOAP
```xml
<?xml version='1.0' encoding='UTF-8'?>
<SOAP-ENV:Envelope
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    SOAP-ENV:encodingStyle="http://schemas.xmlsoap.org/soap/encoding/"
    xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
    xmlns:xsd="http://www.w3.org/2001/XMLSchema">
    <SOAP-ENV:Body>
        <ns1:getServiceNamesResponse
            xmlns:ns1="urn:CONS-SICC-BE">
            <return
                xmlns:ns2="http://schemas.xmlsoap.org/soap/encoding/"
                xsi:type="ns2:Array"
                ns2:arrayType="xsd:string[16]">
                <item xsi:type="xsd:string">ProfiloFascicolo</item>
                <item xsi:type="xsd:string">NotificheDaRitirare</item>
                <item xsi:type="xsd:string">DettaglioComunicazione</item>
                <item xsi:type="xsd:string">RuoliMaterieOggetti</item>
                <item xsi:type="xsd:string">InfoParte</item>
                <item xsi:type="xsd:string">RicercaInformazioniFascicoloPerPartiGiudiceDate</item>
                <item xsi:type="xsd:string">TestWS</item>
                <item xsi:type="xsd:string">ComunicazioneCancelleria</item>
                <item xsi:type="xsd:string">RicercaInformazioniFascicoloPerRMO</item>
                <item xsi:type="xsd:string">DocumentiUtente</item>
                <item xsi:type="xsd:string">Agenda</item>
                <item xsi:type="xsd:string">RicercaInformazioniFascicoloPerTipo</item>
                <item xsi:type="xsd:string">DocumentiFascicolo</item>
                <item xsi:type="xsd:string">StoricoFascicolo</item>
                <item xsi:type="xsd:string">RicercaScadenze</item>
                <item xsi:type="xsd:string">ArchivioFascicoli</item>
            </return>
        </ns1:getServiceNamesResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
