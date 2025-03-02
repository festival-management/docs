# Update Role Paper Size

Questo endpoint permette di aggiornare la dimensione della carta associata a uno specifico ruolo nel sistema. È 
necessario fornire l'ID del ruolo e la nuova dimensione della carta nel corpo della richiesta.

**Permission**: `can_administer`

<api-endpoint openapi-path="./../openapi.yaml" endpoint="/roles/{role_id}/paper_size" method="put">
    <request>
        <sample lang="JSON" title="Payload">
            {
                "role_id": 1,
                "paper_size": "A4"
            }
        </sample>
    </request>
    <response type="200">
        <sample lang="JSON">
            {
                "error": false,
                "code": 0,
                "message": ""
            }
        </sample>
    </response>
    <response type="401">
        <sample lang="JSON">
            {
                "error": true,
                "code": 401,
                "message": ""
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