# Delete Menu Date

Questo endpoint permette di eliminare una specifica data da un menù. Per eliminare una data da un menù, è necessario 
fornire l'ID della data dello specifico menù che si desidera rimuovere.

**Permission**: `can_administer`

<api-endpoint openapi-path="./../openapi.yaml" endpoint="/menus/{menu_id}/date/{menu_date_id}" method="delete">
    <request>
        <sample lang="JSON" title="Payload">
            {
                "menu_id": 1,
                "menu_date_id": 1
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