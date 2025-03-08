# Delete Order

Questo endpoint permette di eliminare un ordine dal sistema. Per eliminare un ordine, è necessario fornire l'ID 
dell'ordine che si desidera rimuovere.

**Permission**: `can_administer`

<api-endpoint openapi-path="./../openapi.yaml" endpoint="/orders/{order_id}" method="delete">
    <request>
        <sample lang="JSON" title="Payload">
            {
                "order_id": 1
            }
        </sample>
    </request>
    <response type="200">
        <sample lang="JSON">
            {
                "error": false,
                "code": 0,
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