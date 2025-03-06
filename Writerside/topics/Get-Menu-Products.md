# Get Menu Products

Questo endpoint permette di ottenere tutti i prodotti riguardanti un menù. Per ottenere i prodotti di un menù è
necessario fornire l'ID del menù che si desidera ottenere. Inoltre ci sono dei parametri che permetto di modificare la
risposta:
- `include_dates`: se impostato su true, aggiungerà un array con tutte le date di validità dei prodotti.
- `include_ingredients`: se impostato su true, aggiungerà un array con tutti gli ingredienti dei prodotti.
- `include_roles`: se impostato su true, aggiungerà un array con tutti i ruoli dei prodotti.
- `include_variants`: se impostato su true, aggiungerà un array con tutte le varianti dei prodotti.

<api-endpoint openapi-path="./../openapi.yaml" endpoint="/menus/{menu_id}/products" method="get">
    <request>
        <sample lang="JSON" title="Payload">
            {
                "menu_id": 1,
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
                "products": [
                    {
                        "id": 1,
                        "price": 1,
                        "product": {
                            "id": 1,
                            "name": "abcde",
                            "short_name": "string",
                            "is_priority": true,
                            "price": 0,
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
                                    "price": 0
                                }
                            ],
                            "roles": [
                                {
                                    "id": 1,
                                    "role_id": 1
                                }
                            ],
                            "variants": [
                                {
                                    "id": 1,
                                    "name": "abcde",
                                    "price": 3
                                }
                            ]
                        }
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