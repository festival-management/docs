# Create Role

<api-endpoint openapi-path="./../openapi.yaml" endpoint="/roles/" method="post">
    <request>
        <sample lang="JSON" title="Payload">
            {
              "name": "abcde"
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
                    "name": "abcde",
                    "permissions": {
                        "can_administer": true,
                        "can_order": false,
                        "can_statistics": true,
                        "can_priority_statistics": false
                    },
                    "paper_size": "A4"
                }
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