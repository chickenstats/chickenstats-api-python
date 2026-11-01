# EmailChangeRequest


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**new_email** | **str** |  | 

## Example

```python
from chickenstats_api.models.email_change_request import EmailChangeRequest

# TODO update the JSON string below
json = "{}"
# create an instance of EmailChangeRequest from a JSON string
email_change_request_instance = EmailChangeRequest.from_json(json)
# print the JSON string representation of the object
print(EmailChangeRequest.to_json())

# convert the object into a dict
email_change_request_dict = email_change_request_instance.to_dict()
# create an instance of EmailChangeRequest from a dict
email_change_request_from_dict = EmailChangeRequest.from_dict(email_change_request_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


