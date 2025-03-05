# Update Product Is Priority

Questo endpoint permette di modificare la priorità di un specifico prodotto nel sistema. È necessario specificare il
prodotto tramite il parametro della path e fornire la nuova priorità nel corpo della richiesta.

**Permission**: `can_administer`

<api-endpoint openapi-path="./../openapi.yaml" endpoint="/products/{product_id}/priority" method="put">
    <request>
        <sample lang="JSON" title="Payload">
            {
                "product_id": 1,
                "is_priority": true
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