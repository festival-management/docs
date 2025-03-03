# Get Roles

Questo endpoint consente di ottenere tutti i ruoli in base ai criteri di ricerca specificati tramite i parametri della 
query. I parametri supportati permettono di filtrare i risultati per gestire la paginazione e selezionare i ruoli in 
base alle loro caratteristiche:
- `offset` e `limit`: utilizzati per paginare i risultati (in combinazione con il frontend), consentendo di recuperare 
  un sottoinsieme dei ruoli (es. per la visualizzazione a pagine).
- `only_name`: se impostato su true, restituirà solo gli ID e i nomi dei ruoli, escludendo altre informazioni.
- `can_order`: se impostato su true, restituirà solo i ruoli che hanno la possibilità di ordinare.

**Permission**: `can_administer`

<api-endpoint openapi-path="./../openapi.yaml" endpoint="/roles/" method="get">
    <request>
        <sample lang="JSON" title="Payload">
            {
                "offset": 1,
                "limit": 2,
                "only_name": true,
                "can_order": true
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
                        "permissions": {
                            "can_administer": true,
                            "can_order": false,
                            "can_statistics": true,
                            "can_priority_statistics": false
                        },
                        "paper_size": "A4"
                    },
                    {
                        "id": 2,
                        "name": "abcdef",
                        "permissions": {
                            "can_administer": true,
                            "can_order": false,
                            "can_statistics": true,
                            "can_priority_statistics": false
                        },
                        "paper_size": "A4"
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