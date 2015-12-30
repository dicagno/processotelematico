#getServiceDescriptor
Ritorna `serviceDescriptorType`, il descrittore del servizio specificato nel body della risposta SOAP.

Richiesta SOAP
```xml
<?xml version='1.0' encoding='UTF-8'?>
<soap-env:Envelope
    xmlns:soap-env="http://schemas.xmlsoap.org/soap/envelope/">
    <soap-env:Header>
        <ws:invocationDomain
            soap-env:actor="http://schemas.xmlsoap.org/soap/actor/next"
            xmlns:ws="http://www.netserv.it/anag/security"
            soap-env:MustUnderstand="true"
            group="jpwusers"
            role="JPW"
            name="JPW">
        </ws:invocationDomain>
    </soap-env:Header>
    <soap-env:Body>
        <m:getServiceDescriptor
            xmlns:m="urn:CONS-SICC-BE">
            <value name="serviceName" type="string">TestWS</value>
        </m:getServiceDescriptor>
    </soap-env:Body>
</soap-env:Envelope>
```

Risposta SOAP
```xml
<?xml version='1.0' encoding='UTF-8'?>
<SOAP-ENV:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    SOAP-ENV:encodingStyle="http://schemas.xmlsoap.org/soap/encoding/"
    xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
    xmlns:xsd="http://www.w3.org/2001/XMLSchema">
    <SOAP-ENV:Body>
        <ns1:getServiceDescriptorResponse xmlns:ns1="urn:CONS-SICC-BE">
            <return
                name="TestWS"
                description="Test web service"
                xmlns:ns2="urn:qbuilder-types"
                xsi:type="ns2:serviceDescriptorType">
                <ns2:params name="idUfficio" type="string" description="codice ufficio"/>
                <ns2:rowClass name="infoTest"/>
            </return>
        </ns1:getServiceDescriptorResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
