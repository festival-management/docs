# Add Product Ingredient

Questo endpoint permette di aggiungere un nuovo ingrediente a un prodotto. Per creare un nuovo ingrediente su un
prodotto bisogna specificare il nome dell'ingrediente e il prezzo da aggiungere al prodotto se si seleziona il 
determinato ingrediente (può essere anche 0).

**Permission**: `can_administer`

<api-endpoint openapi-path="./../openapi.yaml" endpoint="/products/{product_id}/ingredient" method="post">
    <request>
        <sample lang="JSON" title="Payload">
            {
                "product_id": 1,
                "name": "abcde",
                "price": 5.76
            }
        </sample>
    </request>
    <response type="200">
        <sample lang="JSON">
            {
                "error": false,
                "code": 0,
                "message": "",
                "ingredient": {
                    "id": 1,
                    "name": "abcde",
                    "price": 5.76
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