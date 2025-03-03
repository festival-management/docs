# Create Subcategory

Questo endpoint permette di creare una nuova sotto-categoria all'interno del sistema. Per creare una sottocategoria, è 
necessario fornire un nome. Eventuali parametri aggiuntivi (come l'ordine della sotto-categoria) possono essere 
modificati successivamente utilizzando i metodi PUT forniti.

**Permission**: `can_administer`

<api-endpoint openapi-path="./../openapi.yaml" endpoint="/subcategories/" method="post">
    <request>
        <sample lang="JSON" title="Payload">
            {
              "name": "abcde"
            }
        </sample>
    </request>
    <response type="200">
        <sample lang="JSON">
            {
                "error": false,
                "code": 0,
                "message": "",
                "subcategory": {
                    "id": 1,
                    "name": "abcde",
                    "order": 1
                }
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