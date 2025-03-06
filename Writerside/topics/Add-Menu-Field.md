# Add Menu Field

Questo endpoint permette di aggiungere un nuovo campo a un menù. Per creare un nuovo campo su un menù bisogna 
specificare il nome del campo, il numero massimo di elementi ordinabili per il campo e il costo addizionale nel caso in 
cui il numero di prodotto selezionati per il campo superi il numero massimo di elementi ordinabili.

**Permission**: `can_administer`

<api-endpoint openapi-path="./../openapi.yaml" endpoint="/menus/{menu_id}/field" method="post">
    <request>
        <sample lang="JSON" title="Payload">
            {
                "menu_id": 1,
                "name": "abcde",
                "max_sortable_elements": 1,
                "additional_cost": 0,
            }
        </sample>
    </request>
    <response type="200">
        <sample lang="JSON">
            {
                "error": false,
                "code": 0,
                "message": "",
                "field": {
                    "id": 1,
                    "name": "abcde",
                    "max_sortable_elements": 1,
                    "additional_cost": 0,
                    "is_optional": true,
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