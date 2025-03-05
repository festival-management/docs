# Delete Product Ingredient

Questo endpoint permette di eliminare uno specifico ingrediente da un prodotto. Per eliminare un ingrediente da un 
prodotto, è necessario fornire l'ID dell'ingrediente dello specifico prodotto che si desidera rimuovere.

**Permission**: `can_administer`

<api-endpoint openapi-path="./../openapi.yaml" endpoint="/products/{product_id}/ingredient/{product_ingredient_id}" method="delete">
    <request>
        <sample lang="JSON" title="Payload">
            {
                "product_id": 1,
                "product_ingredient_id": 1
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