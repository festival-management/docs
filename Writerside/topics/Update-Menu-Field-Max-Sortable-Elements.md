# Update Menu Field Max Sortable Elements

Questo endpoint permette di modificare il numero massimo di elementi ordinabili di un specifico campo di un menù nel 
sistema. È necessario specificare il menù e il campo del menù tramite il parametro della path e fornire il nuovo numero
massimo di elementi ordinabili nel corpo della richiesta.

**Permission**: `can_administer`

<api-endpoint openapi-path="./../openapi.yaml" endpoint="/menus/{menu_id}/field/{menu_field_id}/max_sortable_elements" method="put">
    <request>
        <sample lang="JSON" title="Payload">
            {
                "menu_id": 1,
                "menu_field_id": 1,
                "max_sortable_elements": 2
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