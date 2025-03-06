# Create Menu

Questo endpoint permette di creare un nuovo menù all'interno del sistema. Per creare un menù, è necessario
fornire un nome, un nome corto, un prezzo. Eventuali parametri aggiuntivi (come date, campi, ecc.) potranno essere 
modificati successivamente utilizzando i metodi PUT forniti.

**Permission**: `can_administer`

<api-endpoint openapi-path="./../openapi.yaml" endpoint="/menus/" method="post">
    <request>
        <sample lang="JSON" title="Payload">
            {
                "name": "abcde",
                "short_name": "abcde",
                "price": 4.99
            }
        </sample>
    </request>
    <response type="200">
        <sample lang="JSON">
            {
                "error": false,
                "code": 0,
                "message": "",
                "menu": {
                    "id": 1,
                    "name": "abcde",
                    "short_name": "abcde",
                    "price": 4.99
                }
            }
        </sample>
    </response>
    <response type="409">
        <sample lang="JSON">
            {
                "error": true,
                "code": 409,
                "message": ""
            }
        </sample>
    </response>
    <response type="422">
        <sample lang="JSON">
            {
                "error": true,
                "code": 422,
                "message": ""
            }
        </sample>
    </response>
</api-endpoint>