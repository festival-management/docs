# Get Menu

Questo endpoint permette di ottenere tutte le informazioni riguardanti un menù (id, name, short_name, price). Per 
ottenere le informazioni di un menù è necessario fornire l'ID del menù che si desidera ottenere. Inoltre ci sono dei 
parametri che permetto di modificare la risposta:
- `include_dates`: se impostato su true, aggiungerà un array con tutte le date di validità del menù.
- `include_fields`: se impostato su true, aggiungerà un array con tutti i campi del menù.
- `include_fields_products`: se impostato su true, aggiungerà un array con tutti i prodotti dei campi del menù.
- `include_fields_products_dates`: se impostato su true, aggiungerà un array con tutte le date dei prodotti dei campi 
  del menù.
- `include_fields_products_ingredients`: se impostato su true, aggiungerà un array con tutti gli ingredienti dei 
  prodotti dei campi del menù.
- `include_fields_products_roles`: se impostato su true, aggiungerà un array con tutti i ruoli dei prodotti dei campi 
  del menù.
- `include_fields_products_variants`: se impostato su true, aggiungerà un array con tutte le varianti dei prodotti dei 
  campi del menù.
- `include_roles`: se impostato su true, aggiungerà un array con tutti i ruoli del menù.

<api-endpoint openapi-path="./../openapi.yaml" endpoint="/menus/{menu_id}" method="get">
    <request>
        <sample lang="JSON" title="Payload">
            {
                "menu_id": 1,
                "include_dates": true,
                "include_fields": true,
                "include_fields_products": true,
                "include_fields_products_dates": true,
                "include_fields_products_ingredients": true,
                "include_fields_products_roles": true,
                "include_fields_products_variants": true,
                "include_roles": true
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
                "price": 4.99,
                "dates": [
                    {
                        "id": 1,
                        "start_date": "2025-02-24T17:57:52.344Z",
                        "end_date": "2025-03-24T17:57:52.344Z"
                    }
                ],
                "fields": [
                    {
                        "id": 1,
                        "name": "string",
                        "max_sortable_elements": 1,
                        "additional_cost": 4,
                        "is_optional": true,
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
                ],
                "roles": [
                    {
                        "id": 1,
                        "role_id": 2
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