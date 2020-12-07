# LaunchDarkly.Api.Model.FeatureFlagConfig
## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**On** | **bool?** |  | [optional] 
**Archived** | **bool?** |  | [optional] 
**Salt** | **string** |  | [optional] 
**Sel** | **string** |  | [optional] 
**LastModified** | **long?** |  | [optional] 
**Version** | **int?** |  | [optional] 
**Targets** | [**List&lt;Target&gt;**](Target.md) |  | [optional] 
**Rules** | [**List&lt;Rule&gt;**](Rule.md) |  | [optional] 
**Fallthrough** | [**Fallthrough**](Fallthrough.md) |  | [optional] 
**OffVariation** | **int?** |  | [optional] 
**Prerequisites** | [**List&lt;Prerequisite&gt;**](Prerequisite.md) |  | [optional] 
**TrackEvents** | **bool?** | Set to true to send detailed event information for this flag. | [optional] 
**TrackEventsFallthrough** | **bool?** | Set to true to send detailed event information when targeting is enabled but no individual targeting rule is matched. | [optional] 
**Site** | [**Site**](Site.md) |  | [optional] 
**EnvironmentName** | **string** |  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

