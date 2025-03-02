# Create Role

Questo endpoint permette di creare un nuovo ruolo all'interno del sistema. Per creare un ruolo, è necessario fornire 
un nome. Eventuali parametri aggiuntivi (come permessi specifici) possono essere modificati successivamente utilizzando 
i metodi PUT forniti.

**Permission**: `can_administer`

<api-endpoint openapi-path="./../openapi.yaml" endpoint="/roles/" method="post">
    <request>
        <sample lang="JSON" title="Payload">
            {
              "name": "abcde"
            }
        </sample>
    </request>
    <response type="200">
        <sample lang="JSON">
            {
                "error": false,
                "code": 0,
                "message": "",
                "role": {
                    "id": 1,
                    "name": "abcde",
                    "permissions": {
                        "can_administer": true,
                        "can_order": false,
                        "can_statistics": true,
                        "can_priority_statistics": false
                    },
                    "paper_size": "A4"
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