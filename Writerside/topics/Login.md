# Login

Questo endpoint consente di eseguire il login utilizzando il protocollo OAuth 2.0, sfruttando l'autenticazione tramite 
nome utente e password. In risposta, se tutte le informazioni sono corrette, verrà aggiunto l'access token.

<api-endpoint openapi-path="./../openapi.yaml" endpoint="/auth/token/" method="post">
    <request>
        <sample lang="JSON" title="Payload">
            {
                "grant_type": "password",
                "username": "johndoe",
                "password": "password123",
                "scope": "read",
                "client_id": "my-client-id",
                "client_secret": "my-client-secret"
            }
        </sample>
    </request>
    <response type="200">
        <sample lang="JSON">
            {
                "error": false,
                "code": 0,
                "message": "",
                "access_token": "...",
                "token_type": "bearer"
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
