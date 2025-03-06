# Add Menu Field Product

Questo endpoint permette di aggiungere un nuovo prodotto a un determinato campo di un menù. Per aggiungere un prodotto a
uno specifico campo di un menù bisogna specificare l'id del prodotto che si vuole aggiungere e il prezzo (può essere 
anche 0) che verrà applicato in caso si selezioni il prodotto al momento dell'ordine.

**Permission**: `can_administer`

<api-endpoint openapi-path="./../openapi.yaml" endpoint="/menus/{menu_id}/field/{menu_field_id}/product" method="post">
    <request>
        <sample lang="JSON" title="Payload">
            {
                "menu_id": 1,
                "menu_field_id": 1,
                "product_id": 1,
                "price": 5,
            }
        </sample>
    </request>
    <response type="200">
        <sample lang="JSON">
            {
                "error": false,
                "code": 0,
                "message": "",
                "field_product": {
                    "id": 1,
                    "price": 5,
                    "product": {
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