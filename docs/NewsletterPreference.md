# NewsletterPreference

The two newsletters, each on or off on its own; None leaves one as it is.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**announcements** | **bool** |  | [optional] 
**paid** | **bool** |  | [optional] 

## Example

```python
from chickenstats_api.models.newsletter_preference import NewsletterPreference

# TODO update the JSON string below
json = "{}"
# create an instance of NewsletterPreference from a JSON string
newsletter_preference_instance = NewsletterPreference.from_json(json)
# print the JSON string representation of the object
print(NewsletterPreference.to_json())

# convert the object into a dict
newsletter_preference_dict = newsletter_preference_instance.to_dict()
# create an instance of NewsletterPreference from a dict
newsletter_preference_from_dict = NewsletterPreference.from_dict(newsletter_preference_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


