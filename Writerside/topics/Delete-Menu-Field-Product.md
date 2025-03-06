# Delete Menu Field Product

Questo endpoint permette di eliminare un specifico prodotto da un campo di un menù. Per eliminare un prodotto da un 
campo, è necessario fornire l'ID del prodotto dello specifico campo del menù che si desidera rimuovere.

**Permission**: `can_administer`

<api-endpoint openapi-path="./../openapi.yaml" endpoint="/menus/{menu_id}/field/{menu_field_id}/product/{menu_field_product_id}" method="delete">
    <request>
        <sample lang="JSON" title="Payload">
            {
                "menu_id": 1,
                "menu_field_id": 1,
                "menu_field_product_id": 1,
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