# Get Role

Questo endpoint permette di ottenere tutte le informazioni riguardanti un ruolo (id, name, permessions, paper_size). Per
ottenere le informazioni di un ruolo è necessario fornire l'ID del ruolo che si desidera ottenere.

**Permission**: `can_administer`

<api-endpoint openapi-path="./../openapi.yaml" endpoint="/roles/{role_id}" method="get">
    <request>
        <sample lang="JSON" title="Payload">
            {
                "role_id": 1
            }
        </sample>
    </request>
    <response type="200">
        <sample lang="JSON">
            {
                "error": false,
                "code": 0,
                "message": "",
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
        </sample>
    </response>
    <response type="404">
        <sample lang="JSON">
            {
                "error": true,
                "code": 404,
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