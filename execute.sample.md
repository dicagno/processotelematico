#execute
Esegue una operazione SOAP e ritorna il risultato di questa, entrambi (operazione e risultato) descritta nel relativo documento WSDL.

###Richiesta SOAP
```xml
<?xml version="1.0" encoding="UTF-8"?>
<soap-env:Envelope
    xmlns:soap-env="http://schemas.xmlsoap.org/soap/envelope/">
    <soap-env:Header>
        <ws:invocationDomain
            xmlns:ws="http://www.netserv.it/anag/security"
            name="JPW"
            role="AVV"
            group="0720060097"
            soap-env:mustUnderstand="true"/>
        </soap-env:Header>
        <soap-env:Body>
            <m:execute
                xmlns:m="urn:CONS-SICC-BE-DISTR">
                <m:name>RicercaInformazioniFascicoloPerTipo</m:name>
                <m:valueSet>
                    <m:value name="idUfficio" type="string">12345678</m:value>
                    <m:value name="idSezione" type="string">1234</m:value>
                    <m:value name="numero" type="string"/>
                    <m:value name="tipo" type="string">RGN</m:value>
                    <m:value name="anno" type="string">1234</m:value>
                    <m:value name="pageSize" type="integer">15</m:value>
                    <m:value name="pageNo" type="integer">1</m:value>
                </m:valueSet>
                <m:orderBy>
                    <m:entry property="annoruolo" mode="asc"/>
                    <m:entry property="numeroruolo" mode="asc"/>
                </m:orderBy>
            </m:execute>
        </soap-env:Body>
    </soap-env:Envelope>
```

###Risposta SOAP
```xml
<?xml version='1.0' encoding='UTF-8'?>
<SOAP-ENV:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" SOAP-ENV:encodingStyle="http://schemas.xmlsoap.org/soap/encoding/" xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
    <SOAP-ENV:Body>
        <ns1:executeResponse xmlns:ns1="urn:CONS-SICC-BE-DISTR">
            <return available="14" time="2015-12-30 17:46:08" xmlns:ns2="http://www.netserv.it/QBuilder/types" xsi:type="ns2:rowListType">
                <ns2:row class="InfoFascicoloExt">
                    <ns2:property name="IDFASCICOLO" type="string">1234567890</ns2:property>
                    <ns2:property name="IDUFFICIO" type="string">12345678</ns2:property>
                    <ns2:property name="ANNORUOLO" type="long">1234</ns2:property>
                    <ns2:property name="NUMERORUOLO" type="string">00001234</ns2:property>
                    <ns2:property name="SUBPROCEDIMENTO" type="string"/>
                    <ns2:property name="DATAUDIENZA" type="date"/>
                    <ns2:property name="GIUDICE" type="string">PINCO PALLINO</ns2:property>
                    <ns2:property name="SEZIONE" type="string">Seconda</ns2:property>
                    <ns2:property name="ATTOREPRINCIPALE" type="string">Azienda SPA </ns2:property>
                    <ns2:property name="CONVENUTOPRINCIPALE" type="string">Ditta SRL </ns2:property>
                    <ns2:property name="NUMEROATTORI" type="long">1</ns2:property>
                    <ns2:property name="NUMEROCONVENUTI" type="long">1</ns2:property>
                    <ns2:property name="DATAULTIMAMODIFICA" type="date">01/01/2001 00:00:00.000</ns2:property>
                    <ns2:subRows class="InfoParte">
                        <ns2:row>
                            <ns2:property name="COGNOME" type="string">Azienda SPA</ns2:property>
                            <ns2:property name="NOME" type="string"/>
                            <ns2:property name="TIPO" type="string">AP</ns2:property>
                            <ns2:property name="DATANASCITA" type="date"/>
                            <ns2:property name="CODICEFISCALEPARTE" type="string">0123456789</ns2:property>
                            <ns2:property name="AVVOCATO" type="string">JOHN DOE</ns2:property>
                            <ns2:property name="CODICEFISCALEAVVOCATO" type="string">JHNDE1237GTADL</ns2:property>
                        </ns2:row>
                        <ns2:row>
                            <ns2:property name="COGNOME" type="string">Ditta SRL</ns2:property>
                            <ns2:property name="NOME" type="string"/>
                            <ns2:property name="TIPO" type="string">CP</ns2:property>
                            <ns2:property name="DATANASCITA" type="date"/>
                            <ns2:property name="CODICEFISCALEPARTE" type="string">9876543210</ns2:property>
                            <ns2:property name="AVVOCATO" type="string">PAPERINO PAOLINO</ns2:property>
                            <ns2:property name="CODICEFISCALEAVVOCATO" type="string">PLNPPR1676ALXK</ns2:property>
                        </ns2:row>
                    </ns2:subRows>
                </ns2:row>
                <ns2:row ...>
                </ns2:row>
            </return>
        </ns1:executeResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
