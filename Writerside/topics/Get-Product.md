# Get Product

Questo endpoint permette di ottenere tutte le informazioni riguardanti un prodotto (id, name, short_name, is_priority, 
price, category e subcategory). Per ottenere le informazioni di un prodotto è necessario fornire l'ID del prodotto che 
si desidera ottenere. Inoltre ci sono dei parametri che permetto di modificare la risposta:
- `include_dates`: se impostato su true, aggiungerà un array con tutte le date di validità del prodotto.
- `include_ingredients`: se impostato su true, aggiungerà un array con tutti gli ingredienti del prodotto.
- `include_roles`: se impostato su true, aggiungerà un array con tutti i ruoli del prodotto.
- `include_variants`: se impostato su true, aggiungerà un array con tutte le varianti del prodotto.

<api-endpoint openapi-path="./../openapi.yaml" endpoint="/products/{product_id}" method="get">
    <request>
        <sample lang="JSON" title="Payload">
            {
                "product_id": 1,
                "include_dates": true,
                "include_ingredients": true,
                "include_roles": true,
                "include_variants": true
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
                "short_name": "abcde",
                "is_priority": false,
                "price": 4.99,
                "category": "food",
                "subcategory_id": 1,
                "dates": [
                    {
                        "id": 1,
                        "start_date": "2025-02-24T17:57:52.344Z",
                        "end_date": "2025-03-24T17:57:52.344Z"
                    }
                ],
                "ingredients": [
                    {
                        "id": 1,
                        "name": "abcde",
                        "price": 5.76
                    }
                ],
                "roles": [
                    {
                        "id": 1,
                        "role_id": 2
                    }
                ],
                "variants": [
                    {
                        "id": 1,
                        "name": "abcde",
                        "price": 4.99
                    }
                ]
            }
        </sample>
    </response>
    <response type="401">
        <sample lang="JSON">
            {
                "error": true,
                "code": 401,
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