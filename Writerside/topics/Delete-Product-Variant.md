# Delete Product Variant

Questo endpoint permette di eliminare una specifica variante da un prodotto. Per eliminare una variante da un
prodotto, è necessario fornire l'ID della variante dello specifico prodotto che si desidera rimuovere.

**Permission**: `can_administer`

<api-endpoint openapi-path="./../openapi.yaml" endpoint="/products/{product_id}/variant/{product_variant_id}" method="delete">
    <request>
        <sample lang="JSON" title="Payload">
            {
                "product_id": 1,
                "product_variant_id": 1
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