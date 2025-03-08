# Create order

Questo endpoint permette di creare un nuovo ordine all'interno del sistema. Per creare un ordine, è necessario fornire
il nome del cliente, il numero di persone per l'ordine, se è per asporto, il tavolo. Il tavolo e il numero di persone 
non sono obbligatorie se l'ordine è per asporto. Inoltre è necessario aggiungere una lista di prodotti e menù per 
l'ordine.

**Permission**: `can_order`

<api-endpoint openapi-path="./../openapi.yaml" endpoint="/orders/" method="post">
    <request>
        <sample lang="JSON" title="Payload">
            {
                "customer": "abcde",
                "guests": 1,
                "is_take_away": false,
                "table": 3,
                "products": [
                    {
                        "product_id": 1,
                        "variant_id": 1,
                        "ingredients": [
                            {
                                "ingredient_id": 1,
                                "quantity": 1,
                            }
                        ],
                        "quantity": 1,
                    }
                ],
                "menus": [
                    {
                        "menu_id": 1,
                        "fields": [
                            {
                                "menu_field_id": 1,
                                "products": [
                                    {
                                        "product_id": 1,
                                        "variant_id": 1,
                                        "ingredients": [
                                            {
                                                "ingredient_id": 1,
                                                "quantity": 1,
                                            }
                                        ],
                                        "quantity": 1,
                                    }
                                ],
                            }
                        ],
                        "quantity": 1,
                    }
                ],
            }
        </sample>
    </request>
    <response type="200">
        <sample lang="JSON">
            {
                "error": false,
                "code": 0,
                "message": "",
                "order": {
                    "id": 1,
                    "customer": "abcde",
                    "guests": 1,
                    "is_take_away": false,
                    "table": 3,
                    "created_at": "2025-03-08T11:39:34.668Z"
                }
            }
        </sample>
    </response>
    <response type="400">
        <sample lang="JSON">
            {
                "error": true,
                "code": 400,
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