# Add Product Variant

Questo endpoint permette di aggiungere una nuova variante a un prodotto. Per creare una nuova variante su un prodotto 
bisogna specificare il nome della variante e il prezzo da aggiungere al prodotto se si seleziona la determinata variante
(può essere anche 0).

**Permission**: `can_administer`

<api-endpoint openapi-path="./../openapi.yaml" endpoint="/products/{product_id}/variant" method="post">
    <request>
        <sample lang="JSON" title="Payload">
            {
                "product_id": 1,
                "name": "abcde",
                "price": 4.99
            }
        </sample>
    </request>
    <response type="200">
        <sample lang="JSON">
            {
                "error": false,
                "code": 0,
                "message": "",
                "variant": {
                    "id": 1,
                    "name": "abcde",
                    "price": 4.99
                }
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