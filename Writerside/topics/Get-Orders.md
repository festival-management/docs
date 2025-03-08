# Get Orders

Questo endpoint consente di ottenere tutti gli ordine in base ai criteri di ricerca specificati tramite i parametri 
della query. I parametri supportati permettono di filtrare i risultati per gestire la paginazione e selezionare gli 
ordini in base alle loro caratteristiche:
- `offset` e `limit`: utilizzati per paginare i risultati (in combinazione con il frontend), consentendo di recuperare
  un sottoinsieme degli ordini (es. per la visualizzazione a pagine).
- `order_by`: se impostato, restituirà gli ordini ordinati in base al parametro messo.
- `include_menus`: se impostato su true, aggiungerà un array con tutti i menù degli ordini.
- `include_menus_menu`: se impostato su true, aggiungerà un campo con il menù di ogni singolo menù degli ordini.
- `include_menus_menu_dates`: se impostato su true, aggiungerà un array con le date del menù di ogni singolo menù degli 
  ordini.
- `include_menus_menu_fields`: se impostato su true, aggiungerà un array con i campi del menù di ogni singolo menù degli 
  ordini.
- `include_menus_menu_fields_products`: se impostato su true, aggiungerà un array con i prodotti dei campi del menù di
  ogni singolo menù degli ordini.
- `include_menus_menu_fields_products_dates`: se impostato su true, aggiungerà un array con le date dei prodotti dei
  campi del menù di ogni singolo menù degli ordini.
- `include_menus_menu_fields_products_ingredients`: se impostato su true, aggiungerà un array con gli ingredienti dei
  prodotti dei campi del menù di ogni singolo menù degli ordini.
- `include_menus_menu_fields_products_roles`: se impostato su true, aggiungerà un array con i ruoli dei prodotti dei
  campi del menù di ogni singolo menù degli ordini.
- `include_menus_menu_fields_products_variants`: se impostato su true, aggiungerà un array con le varianti dei prodotti
  dei campi del menù di ogni singolo menù degli ordini.
- `include_menus_menu_roles`: se impostato su true, aggiungerà un array con i ruoli del menù di ogni singolo menù di un
  ordine.
- `include_menus_fields`: se impostato su true, aggiungerà un array con i campi dei menù degli ordini.
- `include_menus_fields_products`: se impostato su true, aggiungerà un array con i prodotti dei campi dei menù degli 
  ordini.
- `include_menus_fields_products_ingredients`: se impostato su true, aggiungerà un array con gli ingredienti dei
  prodotti dei campi dei menù degli ordini.
- `include_products`: se impostato su true, aggiungerà un array con tutti i prodotti degli ordini.
- `include_products_product`: se impostato su true, aggiungerà un campo con il prodotto di ogni singolo prodotto degli 
  ordini.
- `include_products_product_dates`: se impostato su true, aggiungerà un array con tutte le date di validità del prodotto
  dei prodotti degli ordini.
- `include_products_product_ingredients`: se impostato su true, aggiungerà un array con tutti gli ingredienti del
  prodotto dei prodotti degli ordini.
- `include_products_product_roles`: se impostato su true, aggiungerà un array con tutti i ruoli del prodotto dei
  prodotti degli ordini.
- `include_products_product_variants`: se impostato su true, aggiungerà un array con tutte le varianti del prodotto dei
  prodotti degli ordini.
- `include_products_ingredients`: se impostato su true, aggiungerà un array con tutti gli ingredienti dei prodotti degli 
  ordini.
- `include_user`: se impostato su true, aggiungerà un campo con le informazioni degli utenti che hanno creato gli 
  ordini.

**Permission**: `can_administer`

<api-endpoint openapi-path="./../openapi.yaml" endpoint="/orders/" method="get">
    <request>
        <sample lang="JSON" title="Payload">
            {
                "offset": 1,
                "limit": 10,
                "order_by": "name",
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
                "total_count": 2,
                "orders": [
                    {
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
                ]
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