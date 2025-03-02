# Update Role Permissions

Questo endpoint permette di modificare i permessi di uno specifico ruolo nel sistema. È necessario specificare il ruolo 
tramite il parametro della path e fornire i nuovi permessi nel corpo della richiesta.

**Permission**: `can_administer`

<api-endpoint openapi-path="./../openapi.yaml" endpoint="/roles/{role_id}/permissions" method="put">
    <request>
        <sample lang="JSON" title="Payload">
            {
                "role_id": 1,
                "permissions": {
                    "can_administer": true,
                    "can_order": false,
                    "can_statistics": true,
                    "can_priority_statistics": false
                }
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