# Add Menu Role

Questo endpoint permette di aggiungere un nuovo ruolo a un determinato menù. Per aggiungere un ruolo a un specifico menù
bisogna specificare l'id del ruolo che si vuole aggiungere.

**Permission**: `can_administer`

<api-endpoint openapi-path="./../openapi.yaml" endpoint="/menus/{menu_id}/role" method="post">
    <request>
        <sample lang="JSON" title="Payload">
            {
                "menu_id": 1,
                "role_id": 2
            }
        </sample>
    </request>
    <response type="200">
        <sample lang="JSON">
            {
                "error": false,
                "code": 0,
                "message": "",
                "role": {
                    "id": 1,
                    "role_id": 2
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