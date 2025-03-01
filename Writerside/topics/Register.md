# Register

Questo endpoint consente di registrare un nuovo utente nel sistema. Una volta completata la registrazione, se tutto 
corretto, l'utente sarà aggiunto al database e verranno restituite le informazioni dell'utente appena registrato.
Ogni utente ha un ruolo (come funzionano i ruoli verrà spiegata nel prossimo capitolo).

<api-endpoint openapi-path="./../openapi.yaml" endpoint="/auth/register/" method="post">
    <request>
        <sample lang="JSON" title="Payload">
            {
              "username": "johndoe",
              "password": "password123",
              "role_id": 13
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