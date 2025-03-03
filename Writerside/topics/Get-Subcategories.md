# Get Subcategories

Questo endpoint consente di ottenere tutte le sotto-categorie in base ai criteri di ricerca specificati tramite i 
parametri della query. I parametri supportati permettono di filtrare i risultati per gestire la paginazione e 
selezionare le sotto-categorie in base alle loro caratteristiche:
- `offset` e `limit`: utilizzati per paginare i risultati (in combinazione con il frontend), consentendo di recuperare
  un sottoinsieme delle sotto-categorie (es. per la visualizzazione a pagine).
- `only_name`: se impostato su true, restituirà solo gli ID e i nomi delle sotto-categorie, escludendo altre 
  informazioni.
- `order_by`: se impostato, restituirà le sotto-categorie ordinate in base al parametro specificato.

<api-endpoint openapi-path="./../openapi.yaml" endpoint="/subcategories/" method="get">
    <request>
        <sample lang="JSON" title="Payload">
            {
                "offset": 1,
                "limit": 2,
                "only_name": true,
                "order_by": "name"
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
                "roles": [
                    {
                        "id": 1,
                        "name": "abcde",
                        "order": 1
                    },
                    {
                        "id": 2,
                        "name": "abcdef",
                        "order": 2
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