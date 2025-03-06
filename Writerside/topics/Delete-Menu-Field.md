# Delete Menu Field

Questo endpoint permette di eliminare uno specifico campo da un menù. Per eliminare un campo da un menù, è necessario
fornire l'ID del campo dello specifico menù che si desidera rimuovere.

**Permission**: `can_administer`

<api-endpoint openapi-path="./../openapi.yaml" endpoint="/menus/{menu_id}/field/{menu_field_id}" method="delete">
    <request>
        <sample lang="JSON" title="Payload">
            {
                "menu_id": 1,
                "menu_field_id": 1
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