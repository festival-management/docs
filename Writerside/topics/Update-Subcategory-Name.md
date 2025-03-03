# Update Subcategory Name

Questo endpoint permette di aggiornare il nome di una specifica sotto-categoria nel sistema. È necessario fornire l'ID 
della sotto-categoria e il nuovo nome nel corpo della richiesta.

**Permission**: `can_administer`

<api-endpoint openapi-path="./../openapi.yaml" endpoint="/subcategories/{subcategory_id}/name" method="put">
    <request>
        <sample lang="JSON" title="Payload">
            {
                "subcategory_id": 1,
                "name": "abcde"
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