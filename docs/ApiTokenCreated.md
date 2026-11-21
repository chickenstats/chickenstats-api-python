# ApiTokenCreated


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **str** |  | 
**name** | **str** |  | 
**prefix** | **str** |  | 
**created_at** | **datetime** |  | 
**last_used_at** | **datetime** |  | 
**expires_at** | **datetime** |  | 
**token** | **str** |  | 

## Example

```python
from chickenstats_api.models.api_token_created import ApiTokenCreated

# TODO update the JSON string below
json = "{}"
# create an instance of ApiTokenCreated from a JSON string
api_token_created_instance = ApiTokenCreated.from_json(json)
# print the JSON string representation of the object
print(ApiTokenCreated.to_json())

# convert the object into a dict
api_token_created_dict = api_token_created_instance.to_dict()
# create an instance of ApiTokenCreated from a dict
api_token_created_from_dict = ApiTokenCreated.from_dict(api_token_created_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


