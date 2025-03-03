# Delete Subcategory

Questo endpoint permette di eliminare una sotto-categoria dal sistema. Per eliminare una sotto-categoria, è necessario 
fornire l'ID della sotto-categoria che si desidera rimuovere.

**Permission**: `can_administer`

<api-endpoint openapi-path="./../openapi.yaml" endpoint="/subcategories/{subcategory_id}" method="delete">
    <request>
        <sample lang="JSON" title="Payload">
            {
                "subcategory_id": 1
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