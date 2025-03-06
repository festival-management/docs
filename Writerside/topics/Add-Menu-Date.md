# Add Menu Date

Questo endpoint permette di aggiungere una nuova data in cui un determinato menù è valido. Per creare una nuova data per
uno specifico menù è necessario fornire la data di inizio e la data di fine del range in cui il menù deve essere valido.

**Permission**: `can_administer`

<api-endpoint openapi-path="./../openapi.yaml" endpoint="/menus/{menu_id}/date" method="post">
    <request>
        <sample lang="JSON" title="Payload">
            {
                "menu_id": 1,
                "start_date": "2025-02-24T17:57:52.344Z",
                "end_date": "2025-03-24T17:57:52.344Z"
            }
        </sample>
    </request>
    <response type="200">
        <sample lang="JSON">
            {
                "error": false,
                "code": 0,
                "message": "",
                "date": {
                    "id": 1,
                    "start_date": "2025-02-24T17:57:52.344Z",
                    "end_date": "2025-03-24T17:57:52.344Z"
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