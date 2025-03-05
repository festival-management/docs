# Create Product

Questo endpoint permette di creare un nuovo prodotto all'interno del sistema. Per creare un prodotto, è necessario 
fornire un nome, un nome corto, un prezzo, una categoria, una sotto-categoria. Eventuali parametri aggiuntivi (come 
varianti, ingredienti, ecc.) possono essere modificati successivamente utilizzando i metodi PUT forniti.

**Permission**: `can_administer`

<api-endpoint openapi-path="./../openapi.yaml" endpoint="/products/" method="post">
    <request>
        <sample lang="JSON" title="Payload">
            {
                "name": "abcde",
                "short_name": "abcde",
                "price": 4.99,
                "category": "food",
                "subcategory_id": 1
            }
        </sample>
    </request>
    <response type="200">
        <sample lang="JSON">
            {
                "error": false,
                "code": 0,
                "message": "",
                "product": {
                    "id": 1,
                    "name": "abcde",
                    "short_name": "abcde",
                    "is_priority": false,
                    "price": 4.99,
                    "category": "food",
                    "subcategory_id": 1
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