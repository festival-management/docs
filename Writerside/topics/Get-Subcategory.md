# Get Subcategory

Questo endpoint permette di ottenere tutte le informazioni riguardanti una sotto-categoria (id, name, order). Per 
ottenere le informazioni di una sotto-categoria è necessario fornire l'ID della sotto-categoria che si desidera ottenere.

**Permission**: `can_administer`

<api-endpoint openapi-path="./../openapi.yaml" endpoint="/subcategories/{subcategory_id}" method="get">
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
                "message": "",
                "id": 1,
                "name": "abcde",
                "order": 1
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