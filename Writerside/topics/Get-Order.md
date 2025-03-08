# Get Order

Questo endpoint permette di ottenere tutte le informazioni riguardanti un ordine. Per ottenere le informazioni di un 
ordine è necessario fornire l'ID dell'ordine che si desidera ottenere. Inoltre ci sono dei parametri che permetto di 
modificare la risposta:
- `include_menus`: se impostato su true, aggiungerà un array con tutti i menù di un ordine.
- `include_menus_menu`: se impostato su true, aggiungerà un campo con il menù di ogni singolo menù di un ordine.
- `include_menus_menu_dates`: se impostato su true, aggiungerà un array con le date del menù di ogni singolo menù di un 
  ordine.
- `include_menus_menu_fields`: se impostato su true, aggiungerà un array con i campi del menù di ogni singolo menù di un
  ordine.
- `include_menus_menu_fields_products`: se impostato su true, aggiungerà un array con i prodotti dei campi del menù di 
  ogni singolo menù di un ordine.
- `include_menus_menu_fields_products_dates`: se impostato su true, aggiungerà un array con le date dei prodotti dei 
  campi del menù di ogni singolo menù di un ordine.
- `include_menus_menu_fields_products_ingredients`: se impostato su true, aggiungerà un array con gli ingredienti dei 
  prodotti dei campi del menù di ogni singolo menù di un ordine.
- `include_menus_menu_fields_products_roles`: se impostato su true, aggiungerà un array con i ruoli dei prodotti dei 
  campi del menù di ogni singolo menù di un ordine.
- `include_menus_menu_fields_products_variants`: se impostato su true, aggiungerà un array con le varianti dei prodotti 
  dei campi del menù di ogni singolo menù di un ordine.
- `include_menus_menu_roles`: se impostato su true, aggiungerà un array con i ruoli del menù di ogni singolo menù di un
  ordine.
- `include_menus_fields`: se impostato su true, aggiungerà un array con i campi dei menù di un ordine.
- `include_menus_fields_products`: se impostato su true, aggiungerà un array con i prodotti dei campi dei menù di un 
  ordine.
- `include_menus_fields_products_ingredients`: se impostato su true, aggiungerà un array con gli ingredienti dei 
  prodotti dei campi dei menù di un ordine.
- `include_products`: se impostato su true, aggiungerà un array con tutti i prodotti di un ordine.
- `include_products_product`: se impostato su true, aggiungerà un campo con il prodotto di ogni singolo prodotto di un 
  ordine.
- `include_products_product_dates`: se impostato su true, aggiungerà un array con tutte le date di validità del prodotto
  dei prodotti di un ordine.
- `include_products_product_ingredients`: se impostato su true, aggiungerà un array con tutti gli ingredienti del 
  prodotto dei prodotti di un ordine.
- `include_products_product_roles`: se impostato su true, aggiungerà un array con tutti i ruoli del prodotto dei 
  prodotti di un ordine.
- `include_products_product_variants`: se impostato su true, aggiungerà un array con tutte le varianti del prodotto dei 
  prodotti di un ordine.
- `include_products_ingredients`: se impostato su true, aggiungerà un array con tutti gli ingredienti dei prodotti di un
  ordine.
- `include_user`: se impostato su true, aggiungerà un campo con le informazioni dell'utente che ha creato l'ordine.

**Permission**: `can_administer`

<api-endpoint openapi-path="./../openapi.yaml" endpoint="/orders/{order_id}" method="get">
    <request>
        <sample lang="JSON" title="Payload">
            {
                "order_id": 1,
                "include_menus": true,
                "include_menus_menu": true,
                "include_menus_menu_dates": true,
                "include_menus_menu_fields": true,
                "include_menus_menu_fields_products": true,
                "include_menus_menu_fields_products_dates": true,
                "include_menus_menu_fields_products_ingredients": true,
                "include_menus_menu_fields_products_roles": true,
                "include_menus_menu_fields_products_variants": true,
                "include_menus_menu_roles": true,
                "include_menus_fields": true,
                "include_menus_fields_products": true,
                "include_menus_fields_products_ingredients": true,
                "include_products": true,
                "include_products_product": true,
                "include_products_product_dates": true,
                "include_products_product_ingredients": true,
                "include_products_product_roles": true,
                "include_products_product_variants": true,
                "include_products_ingredients": true,
                "include_user": true,
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
                "customer": "abcde",
                "guests": 1,
                "is_take_away": true,
                "table": 1,
                "user": {
                    "id": 1,
                    "username": "abcde",
                    "role_id": 1,
                    "created_at": "2025-03-08T12:15:10.627Z"
                },
                "menus": [
                    {
                        "id": 1,
                        "price": 2,
                        "quantity": 2,
                        "menu": {
                            "id": 1,
                            "name": "abcde",
                            "short_name": "abcde",
                            "price": 2,
                            "dates": [
                                {
                                    "id": 1,
                                    "start_date": "2025-03-08T12:15:10.627Z",
                                    "end_date": "2025-03-08T12:15:10.627Z"
                                }
                            ],
                            "fields": [
                                {
                                    "id": 1,
                                    "name": "abcde",
                                    "max_sortable_elements": 1,
                                    "additional_cost": 1,
                                    "is_optional": true,
                                    "products": [
                                        {
                                            "id": 1,
                                            "price": 5,
                                            "product": {
                                                "id": 1,
                                                "name": "abcde",
                                                "short_name": "abcde",
                                                "is_priority": true,
                                                "price": 5,
                                                "category": "food",
                                                "subcategory_id": 1,
                                                "dates": [
                                                    {
                                                        "id": 1,
                                                        "start_date": "2025-03-08T12:15:10.628Z",
                                                        "end_date": "2025-03-08T12:15:10.628Z"
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
                                                        "price": 0
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
                                    "role_id": 1
                                }
                            ]
                        },
                        "fields": [
                            {
                                "id": 1,
                                "menu_field_id": 1,
                                "products": [
                                    {
                                        "id": 1,
                                        "product_id": 1,
                                        "price": 1,
                                        "quantity": 1,
                                        "variant_id": 1,
                                        "order_menu_field_id": 1,
                                        "product": {
                                            "id": 1,
                                            "name": "abcde",
                                            "short_name": "abcde",
                                            "is_priority": true,
                                            "price": 1,
                                            "category": "food",
                                            "subcategory_id": 1,
                                            "dates": [
                                                {
                                                    "id": 1,
                                                    "start_date": "2025-03-08T12:15:10.628Z",
                                                    "end_date": "2025-03-08T12:15:10.628Z"
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
                                                    "price": 0
                                                }
                                            ]
                                        },
                                        "ingredients": [
                                            {
                                                "id": 1,
                                                "product_ingredient_id": 1,
                                                "quantity": 1
                                            }
                                        ]
                                    }
                                ]
                            }
                        ]
                    }
                ],
                "products": [
                    {
                        "id": 1,
                        "product_id": 1,
                        "price": 1,
                        "quantity": 1,
                        "variant_id": 1,
                        "order_menu_field_id": 1,
                        "product": {
                            "id": 1,
                            "name": "abcde",
                            "short_name": "abcde",
                            "is_priority": true,
                            "price": 1,
                            "category": "food",
                            "subcategory_id": 1,
                            "dates": [
                                {
                                    "id": 1,
                                    "start_date": "2025-03-08T12:15:10.628Z",
                                    "end_date": "2025-03-08T12:15:10.628Z"
                                }
                            ],
                            "ingredients": [
                                {
                                    "id": 1,
                                    "name": "string",
                                    "price": 1
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
                                    "price": 0
                                }
                            ]
                        },
                        "ingredients": [
                            {
                                "id": 1,
                                "product_ingredient_id": 1,
                                "quantity": 1
                            }
                        ]
                    }
                ],
                "created_at": "2025-03-08T12:15:10.628Z"
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