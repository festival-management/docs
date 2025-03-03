# Get User

Questo endpoint permette di ottenere tutte le informazioni riguardanti un utente (id, username, ruolo, ecc.). Per
ottenere le informazioni di un utente è necessario fornire l'ID dell'utente che si desidera ottenere.

<api-endpoint openapi-path="./../openapi.yaml" endpoint="/users/{user_id}" method="get">
    <request>
        <sample lang="JSON" title="Payload">
            {
                "user_id": 1
            }
        </sample>
    </request>
    <response type="200">
        <sample lang="JSON">
            {
                "error": false,
                "code": 0,
                "message": "",
                "user": {
                    "id": 1,
                    "username": "johndoe",
                    "role_id": 13,
                    "created_at": "2025-02-24T17:57:52.344Z"
                }
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