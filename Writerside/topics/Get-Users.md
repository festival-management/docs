# Get Users

Questo endpoint consente di ottenere tutti gli utenti presenti nel database (escluso l'utente admin) in base ai criteri 
di ricerca specificati tramite i parametri della query. I parametri supportati permettono di filtrare i risultati per 
gestire la paginazione e selezionare gli utenti in base alle loro caratteristiche:
- `offset` e `limit`: utilizzati per paginare i risultati (in combinazione con il frontend), consentendo di recuperare
  un sottoinsieme degli utenti (es. per la visualizzazione a pagine).

**Permission**: `can_administer`

<api-endpoint openapi-path="./../openapi.yaml" endpoint="/users/" method="get">
    <request>
        <sample lang="JSON" title="Payload">
            {
                "offset": 1,
                "limit": 10
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
                "users": [
                    {
                        "id": 1,
                        "username": "johndoe",
                        "role_id": 13,
                        "created_at": "2025-02-24T17:57:52.344Z"
                    },
                    {
                        "id": 2,
                        "username": "abcde",
                        "role_id": 10,
                        "created_at": "2024-06-12T13:10:52.344Z"
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