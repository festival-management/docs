# Get Products

Questo endpoint consente di ottenere tutti i prodotti in base ai criteri di ricerca specificati tramite i parametri 
della query. I parametri supportati permettono di filtrare i risultati per gestire la paginazione e selezionare i 
prodotti in base alle loro caratteristiche:
- `offset` e `limit`: utilizzati per paginare i risultati (in combinazione con il frontend), consentendo di recuperare
  un sottoinsieme dei prodotti (es. per la visualizzazione a pagine).
- `only_name`: se impostato su true, restituirà solo gli ID e i nomi dei prodotti, escludendo altre informazioni.
- `order_by`: se impostato, restituirà i prodotti ordinati in base al parametro messo.
- `subcategory_id`: se impostato, restituirà solo i prodotti della determinata sotto-categoria messa.
- `include_dates`: se impostato su true, aggiungerà un array con tutte le date di validità dei prodotti.
- `include_ingredients`: se impostato su true, aggiungerà un array con tutti gli ingredienti dei prodotti.
- `include_roles`: se impostato su true, aggiungerà un array con tutti i ruoli dei prodotti.
- `include_variants`: se impostato su true, aggiungerà un array con tutte le varianti dei prodotti.

<api-endpoint openapi-path="./../openapi.yaml" endpoint="/products/" method="get">
    <request>
        <sample lang="JSON" title="Payload">
            {
                "offset": 1,
                "limit": 10,
                "only_name": true,
                "order_by": "name",
                "subcategory_id": 1,
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
                "total_count": 2,
                "products": [
                    {
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
                    },
                    {
                        "id": 2,
                        "name": "abcdef",
                        "short_name": "abcdef",
                        "is_priority": false,
                        "price": 7.99,
                        "category": "food",
                        "subcategory_id": 1,
                        "dates": [],
                        "ingredients": [],
                        "roles": [],
                        "variants": []
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