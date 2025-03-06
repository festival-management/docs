# Update Menu Field Is Optional

Questo endpoint permette di modificare se un campo di un menù del sistema è opzionale. È necessario specificare il menù 
e il campo del menù tramite il parametro della path e fornire il nuovo valore del campo opzionale nel corpo della 
richiesta.

**Permission**: `can_administer`

<api-endpoint openapi-path="./../openapi.yaml" endpoint="/menus/{menu_id}/field/{menu_field_id}/is_optional" method="put">
    <request>
        <sample lang="JSON" title="Payload">
            {
                "menu_id": 1,
                "menu_field_id": 1,
                "is_optional": false
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