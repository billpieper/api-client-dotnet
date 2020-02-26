This repository contains a client library for LaunchDarkly's REST API. This client was automatically
generated from our [OpenAPI specification](https://github.com/launchdarkly/ld-openapi).

This REST API is for custom integrations, data export, or automating your feature flag workflows. *DO NOT* use this client library to include feature flags in your web or mobile application. To integrate feature flags with your application, please see the [SDK documentation](https://docs.launchdarkly.com/v2.0/docs)

# LaunchDarkly.Api - the C# library for the LaunchDarkly REST API

Build custom integrations with the LaunchDarkly REST API

This C# SDK is automatically generated by the [Swagger Codegen](https://github.com/swagger-api/swagger-codegen) project:

- API version: 2.0.30
- SDK version: 1.0.0
- Build package: io.swagger.codegen.languages.CsharpDotNet2ClientCodegen
    For more information, please visit [https://support.launchdarkly.com](https://support.launchdarkly.com)

<a name="frameworks-supported"></a>
## Frameworks supported
- .NET 2.0

<a name="dependencies"></a>
## Dependencies
- Mono compiler
- Newtonsoft.Json.7.0.1
- RestSharp.Net2.1.1.11

Note: NuGet is downloaded by the mono compilation script and packages are installed with it. No dependency DLLs are bundled with this generator

<a name="installation"></a>
## Installation
Run the following command to generate the DLL
- [Mac/Linux] `/bin/sh compile-mono.sh`
- [Windows] TODO

Then include the DLL (under the `bin` folder) in the C# project, and use the namespaces:
```csharp
using LaunchDarkly.Api.Api;
using LaunchDarkly.Api.Client;
using LaunchDarkly.Api.Model;
```
<a name="getting-started"></a>
## Getting Started

```csharp
using System;
using System.Diagnostics;
using LaunchDarkly.Api.Api;
using LaunchDarkly.Api.Client;
using LaunchDarkly.Api.Model;

namespace Example
{
    public class Example
    {
        public void main()
        {
            
            // Configure API key authorization: Token
            Configuration.Default.ApiKey.Add("Authorization", "YOUR_API_KEY");
            // Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
            // Configuration.Default.ApiKeyPrefix.Add("Authorization", "Bearer");

            var apiInstance = new AuditLogApi();
            var before = 789;  // long? | A timestamp filter, expressed as a Unix epoch time in milliseconds. All entries returned will have before this timestamp. (optional) 
            var after = 789;  // long? | A timestamp filter, expressed as a Unix epoch time in milliseconds. All entries returned will have occured after this timestamp. (optional) 
            var q = q_example;  // string | Text to search for. You can search for the full or partial name of the resource involved or fullpartial email address of the member who made the change. (optional) 
            var limit = 8.14;  // decimal? | A limit on the number of audit log entries to be returned, between 1 and 20. (optional) 
            var spec = spec_example;  // string | A resource specifier, allowing you to filter audit log listings by resource. (optional) 

            try
            {
                // Get a list of all audit log entries. The query parameters allow you to restrict the returned results by date ranges, resource specifiers, or a full-text search query.
                AuditLogEntries result = apiInstance.GetAuditLogEntries(before, after, q, limit, spec);
                Debug.WriteLine(result);
            }
            catch (Exception e)
            {
                Debug.Print("Exception when calling AuditLogApi.GetAuditLogEntries: " + e.Message );
            }
        }
    }
}
```

<a name="documentation-for-api-endpoints"></a>
## Documentation for API Endpoints

All URIs are relative to *https://app.launchdarkly.com/api/v2*

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*AuditLogApi* | [**GetAuditLogEntries**](docs/AuditLogApi.md#getauditlogentries) | **GET** /auditlog | Get a list of all audit log entries. The query parameters allow you to restrict the returned results by date ranges, resource specifiers, or a full-text search query.
*AuditLogApi* | [**GetAuditLogEntry**](docs/AuditLogApi.md#getauditlogentry) | **GET** /auditlog/{resourceId} | Use this endpoint to fetch a single audit log entry by its resouce ID.
*CustomRolesApi* | [**DeleteCustomRole**](docs/CustomRolesApi.md#deletecustomrole) | **DELETE** /roles/{customRoleKey} | Delete a custom role by key.
*CustomRolesApi* | [**GetCustomRole**](docs/CustomRolesApi.md#getcustomrole) | **GET** /roles/{customRoleKey} | Get one custom role by key.
*CustomRolesApi* | [**GetCustomRoles**](docs/CustomRolesApi.md#getcustomroles) | **GET** /roles | Return a complete list of custom roles.
*CustomRolesApi* | [**PatchCustomRole**](docs/CustomRolesApi.md#patchcustomrole) | **PATCH** /roles/{customRoleKey} | Modify a custom role by key.
*CustomRolesApi* | [**PostCustomRole**](docs/CustomRolesApi.md#postcustomrole) | **POST** /roles | Create a new custom role.
*CustomerMetricsApi* | [**GetEvaluations**](docs/CustomerMetricsApi.md#getevaluations) | **GET** /usage/evaluations/{envId}/{flagKey} | Get events usage by event id and the feature flag key.
*CustomerMetricsApi* | [**GetEvent**](docs/CustomerMetricsApi.md#getevent) | **GET** /usage/events/{type} | Get events usage by event type.
*CustomerMetricsApi* | [**GetEvents**](docs/CustomerMetricsApi.md#getevents) | **GET** /usage/events | Get events usage endpoints.
*CustomerMetricsApi* | [**GetMAU**](docs/CustomerMetricsApi.md#getmau) | **GET** /usage/mau | Get monthly active user data.
*CustomerMetricsApi* | [**GetMAUByCategory**](docs/CustomerMetricsApi.md#getmaubycategory) | **GET** /usage/mau/bycategory | Get monthly active user data by category.
*CustomerMetricsApi* | [**GetStream**](docs/CustomerMetricsApi.md#getstream) | **GET** /usage/streams/{source} | Get a stream endpoint and return timeseries data.
*CustomerMetricsApi* | [**GetStreamBySDK**](docs/CustomerMetricsApi.md#getstreambysdk) | **GET** /usage/streams/{source}/bysdkversion | Get a stream timeseries data by source show sdk version metadata.
*CustomerMetricsApi* | [**GetStreamSDKVersion**](docs/CustomerMetricsApi.md#getstreamsdkversion) | **GET** /usage/streams/{source}/sdkversions | Get a stream timeseries data by source and show all sdk version associated.
*CustomerMetricsApi* | [**GetStreams**](docs/CustomerMetricsApi.md#getstreams) | **GET** /usage/streams | Returns a list of all streams.
*CustomerMetricsApi* | [**GetUsage**](docs/CustomerMetricsApi.md#getusage) | **GET** /usage | Returns of the usage endpoints available.
*DataExportDestinationsApi* | [**DeleteDestination**](docs/DataExportDestinationsApi.md#deletedestination) | **DELETE** /destinations/{projectKey}/{environmentKey}/{destinationId} | Get a single data export destination by ID
*DataExportDestinationsApi* | [**GetDestination**](docs/DataExportDestinationsApi.md#getdestination) | **GET** /destinations/{projectKey}/{environmentKey}/{destinationId} | Get a single data export destination by ID
*DataExportDestinationsApi* | [**GetDestinations**](docs/DataExportDestinationsApi.md#getdestinations) | **GET** /destinations | Returns a list of all data export destinations.
*DataExportDestinationsApi* | [**PatchDestination**](docs/DataExportDestinationsApi.md#patchdestination) | **PATCH** /destinations/{projectKey}/{environmentKey}/{destinationId} | Perform a partial update to a data export destination.
*DataExportDestinationsApi* | [**PostDestination**](docs/DataExportDestinationsApi.md#postdestination) | **POST** /destinations/{projectKey}/{environmentKey} | Create a new data export destination
*EnvironmentsApi* | [**DeleteEnvironment**](docs/EnvironmentsApi.md#deleteenvironment) | **DELETE** /projects/{projectKey}/environments/{environmentKey} | Delete an environment in a specific project.
*EnvironmentsApi* | [**GetEnvironment**](docs/EnvironmentsApi.md#getenvironment) | **GET** /projects/{projectKey}/environments/{environmentKey} | Get an environment given a project and key.
*EnvironmentsApi* | [**PatchEnvironment**](docs/EnvironmentsApi.md#patchenvironment) | **PATCH** /projects/{projectKey}/environments/{environmentKey} | Modify an environment by ID.
*EnvironmentsApi* | [**PostEnvironment**](docs/EnvironmentsApi.md#postenvironment) | **POST** /projects/{projectKey}/environments | Create a new environment in a specified project with a given name, key, and swatch color.
*FeatureFlagsApi* | [**CopyFeatureFlag**](docs/FeatureFlagsApi.md#copyfeatureflag) | **POST** /flags/{projectKey}/{featureFlagKey}/copy | Copies the feature flag configuration from one environment to the same feature flag in another environment.
*FeatureFlagsApi* | [**DeleteFeatureFlag**](docs/FeatureFlagsApi.md#deletefeatureflag) | **DELETE** /flags/{projectKey}/{featureFlagKey} | Delete a feature flag in all environments. Be careful- - only delete feature flags that are no longer being used by your application.
*FeatureFlagsApi* | [**GetFeatureFlag**](docs/FeatureFlagsApi.md#getfeatureflag) | **GET** /flags/{projectKey}/{featureFlagKey} | Get a single feature flag by key.
*FeatureFlagsApi* | [**GetFeatureFlagStatus**](docs/FeatureFlagsApi.md#getfeatureflagstatus) | **GET** /flag-statuses/{projectKey}/{environmentKey}/{featureFlagKey} | Get the status for a particular feature flag.
*FeatureFlagsApi* | [**GetFeatureFlagStatusAcrossEnvironments**](docs/FeatureFlagsApi.md#getfeatureflagstatusacrossenvironments) | **GET** /flag-status/{projectKey}/{featureFlagKey} | Get the status for a particular feature flag across environments
*FeatureFlagsApi* | [**GetFeatureFlagStatuses**](docs/FeatureFlagsApi.md#getfeatureflagstatuses) | **GET** /flag-statuses/{projectKey}/{environmentKey} | Get a list of statuses for all feature flags. The status includes the last time the feature flag was requested, as well as the state of the flag.
*FeatureFlagsApi* | [**GetFeatureFlags**](docs/FeatureFlagsApi.md#getfeatureflags) | **GET** /flags/{projectKey} | Get a list of all features in the given project.
*FeatureFlagsApi* | [**PatchFeatureFlag**](docs/FeatureFlagsApi.md#patchfeatureflag) | **PATCH** /flags/{projectKey}/{featureFlagKey} | Perform a partial update to a feature.
*FeatureFlagsApi* | [**PostFeatureFlag**](docs/FeatureFlagsApi.md#postfeatureflag) | **POST** /flags/{projectKey} | Creates a new feature flag.
*ProjectsApi* | [**DeleteProject**](docs/ProjectsApi.md#deleteproject) | **DELETE** /projects/{projectKey} | Delete a project by key. Caution- - deleting a project will delete all associated environments and feature flags. You cannot delete the last project in an account.
*ProjectsApi* | [**GetProject**](docs/ProjectsApi.md#getproject) | **GET** /projects/{projectKey} | Fetch a single project by key.
*ProjectsApi* | [**GetProjects**](docs/ProjectsApi.md#getprojects) | **GET** /projects | Returns a list of all projects in the account.
*ProjectsApi* | [**PatchProject**](docs/ProjectsApi.md#patchproject) | **PATCH** /projects/{projectKey} | Modify a project by ID.
*ProjectsApi* | [**PostProject**](docs/ProjectsApi.md#postproject) | **POST** /projects | Create a new project with the given key and name.
*RootApi* | [**GetRoot**](docs/RootApi.md#getroot) | **GET** / | 
*TeamMembersApi* | [**DeleteMember**](docs/TeamMembersApi.md#deletemember) | **DELETE** /members/{memberId} | Delete a team member by ID.
*TeamMembersApi* | [**GetMember**](docs/TeamMembersApi.md#getmember) | **GET** /members/{memberId} | Get a single team member by ID.
*TeamMembersApi* | [**GetMembers**](docs/TeamMembersApi.md#getmembers) | **GET** /members | Returns a list of all members in the account.
*TeamMembersApi* | [**PatchMember**](docs/TeamMembersApi.md#patchmember) | **PATCH** /members/{memberId} | Modify a team member by ID.
*TeamMembersApi* | [**PostMembers**](docs/TeamMembersApi.md#postmembers) | **POST** /members | Invite new members.
*UserSegmentsApi* | [**DeleteUserSegment**](docs/UserSegmentsApi.md#deleteusersegment) | **DELETE** /segments/{projectKey}/{environmentKey}/{userSegmentKey} | Delete a user segment.
*UserSegmentsApi* | [**GetUserSegment**](docs/UserSegmentsApi.md#getusersegment) | **GET** /segments/{projectKey}/{environmentKey}/{userSegmentKey} | Get a single user segment by key.
*UserSegmentsApi* | [**GetUserSegments**](docs/UserSegmentsApi.md#getusersegments) | **GET** /segments/{projectKey}/{environmentKey} | Get a list of all user segments in the given project.
*UserSegmentsApi* | [**PatchUserSegment**](docs/UserSegmentsApi.md#patchusersegment) | **PATCH** /segments/{projectKey}/{environmentKey}/{userSegmentKey} | Perform a partial update to a user segment.
*UserSegmentsApi* | [**PostUserSegment**](docs/UserSegmentsApi.md#postusersegment) | **POST** /segments/{projectKey}/{environmentKey} | Creates a new user segment.
*UserSettingsApi* | [**GetUserFlagSetting**](docs/UserSettingsApi.md#getuserflagsetting) | **GET** /users/{projectKey}/{environmentKey}/{userKey}/flags/{featureFlagKey} | Fetch a single flag setting for a user by key.
*UserSettingsApi* | [**GetUserFlagSettings**](docs/UserSettingsApi.md#getuserflagsettings) | **GET** /users/{projectKey}/{environmentKey}/{userKey}/flags | Fetch a single flag setting for a user by key.
*UserSettingsApi* | [**PutFlagSetting**](docs/UserSettingsApi.md#putflagsetting) | **PUT** /users/{projectKey}/{environmentKey}/{userKey}/flags/{featureFlagKey} | Specifically enable or disable a feature flag for a user based on their key.
*UsersApi* | [**DeleteUser**](docs/UsersApi.md#deleteuser) | **DELETE** /users/{projectKey}/{environmentKey}/{userKey} | Delete a user by ID.
*UsersApi* | [**GetSearchUsers**](docs/UsersApi.md#getsearchusers) | **GET** /user-search/{projectKey}/{environmentKey} | Search users in LaunchDarkly based on their last active date, or a search query. It should not be used to enumerate all users in LaunchDarkly- - use the List users API resource.
*UsersApi* | [**GetUser**](docs/UsersApi.md#getuser) | **GET** /users/{projectKey}/{environmentKey}/{userKey} | Get a user by key.
*UsersApi* | [**GetUsers**](docs/UsersApi.md#getusers) | **GET** /users/{projectKey}/{environmentKey} | List all users in the environment. Includes the total count of users. In each page, there will be up to 'limit' users returned (default 20). This is useful for exporting all users in the system for further analysis. Paginated collections will include a next link containing a URL with the next set of elements in the collection.
*WebhooksApi* | [**DeleteWebhook**](docs/WebhooksApi.md#deletewebhook) | **DELETE** /webhooks/{resourceId} | Delete a webhook by ID.
*WebhooksApi* | [**GetWebhook**](docs/WebhooksApi.md#getwebhook) | **GET** /webhooks/{resourceId} | Get a webhook by ID.
*WebhooksApi* | [**GetWebhooks**](docs/WebhooksApi.md#getwebhooks) | **GET** /webhooks | Fetch a list of all webhooks.
*WebhooksApi* | [**PatchWebhook**](docs/WebhooksApi.md#patchwebhook) | **PATCH** /webhooks/{resourceId} | Modify a webhook by ID.
*WebhooksApi* | [**PostWebhook**](docs/WebhooksApi.md#postwebhook) | **POST** /webhooks | Create a webhook.


<a name="documentation-for-models"></a>
## Documentation for Models

 - [LaunchDarkly.Api.Model.AuditLogEntries](docs/AuditLogEntries.md)
 - [LaunchDarkly.Api.Model.AuditLogEntry](docs/AuditLogEntry.md)
 - [LaunchDarkly.Api.Model.AuditLogEntryTarget](docs/AuditLogEntryTarget.md)
 - [LaunchDarkly.Api.Model.Clause](docs/Clause.md)
 - [LaunchDarkly.Api.Model.CopyActions](docs/CopyActions.md)
 - [LaunchDarkly.Api.Model.CustomProperty](docs/CustomProperty.md)
 - [LaunchDarkly.Api.Model.CustomPropertyValues](docs/CustomPropertyValues.md)
 - [LaunchDarkly.Api.Model.CustomRole](docs/CustomRole.md)
 - [LaunchDarkly.Api.Model.CustomRoleBody](docs/CustomRoleBody.md)
 - [LaunchDarkly.Api.Model.CustomRoles](docs/CustomRoles.md)
 - [LaunchDarkly.Api.Model.Destination](docs/Destination.md)
 - [LaunchDarkly.Api.Model.DestinationAmazonKinesis](docs/DestinationAmazonKinesis.md)
 - [LaunchDarkly.Api.Model.DestinationBody](docs/DestinationBody.md)
 - [LaunchDarkly.Api.Model.DestinationGooglePubSub](docs/DestinationGooglePubSub.md)
 - [LaunchDarkly.Api.Model.DestinationMParticle](docs/DestinationMParticle.md)
 - [LaunchDarkly.Api.Model.DestinationSegment](docs/DestinationSegment.md)
 - [LaunchDarkly.Api.Model.Destinations](docs/Destinations.md)
 - [LaunchDarkly.Api.Model.Environment](docs/Environment.md)
 - [LaunchDarkly.Api.Model.EnvironmentPost](docs/EnvironmentPost.md)
 - [LaunchDarkly.Api.Model.EvaluationUsageError](docs/EvaluationUsageError.md)
 - [LaunchDarkly.Api.Model.Events](docs/Events.md)
 - [LaunchDarkly.Api.Model.Fallthrough](docs/Fallthrough.md)
 - [LaunchDarkly.Api.Model.FeatureFlag](docs/FeatureFlag.md)
 - [LaunchDarkly.Api.Model.FeatureFlagBody](docs/FeatureFlagBody.md)
 - [LaunchDarkly.Api.Model.FeatureFlagConfig](docs/FeatureFlagConfig.md)
 - [LaunchDarkly.Api.Model.FeatureFlagCopyBody](docs/FeatureFlagCopyBody.md)
 - [LaunchDarkly.Api.Model.FeatureFlagCopyObject](docs/FeatureFlagCopyObject.md)
 - [LaunchDarkly.Api.Model.FeatureFlagStatus](docs/FeatureFlagStatus.md)
 - [LaunchDarkly.Api.Model.FeatureFlagStatusAcrossEnvironments](docs/FeatureFlagStatusAcrossEnvironments.md)
 - [LaunchDarkly.Api.Model.FeatureFlagStatusForQueriedEnvironment](docs/FeatureFlagStatusForQueriedEnvironment.md)
 - [LaunchDarkly.Api.Model.FeatureFlagStatuses](docs/FeatureFlagStatuses.md)
 - [LaunchDarkly.Api.Model.FeatureFlags](docs/FeatureFlags.md)
 - [LaunchDarkly.Api.Model.FlagListItem](docs/FlagListItem.md)
 - [LaunchDarkly.Api.Model.Id](docs/Id.md)
 - [LaunchDarkly.Api.Model.Link](docs/Link.md)
 - [LaunchDarkly.Api.Model.Links](docs/Links.md)
 - [LaunchDarkly.Api.Model.MAU](docs/MAU.md)
 - [LaunchDarkly.Api.Model.MAUMetadata](docs/MAUMetadata.md)
 - [LaunchDarkly.Api.Model.MAUbyCategory](docs/MAUbyCategory.md)
 - [LaunchDarkly.Api.Model.Member](docs/Member.md)
 - [LaunchDarkly.Api.Model.Members](docs/Members.md)
 - [LaunchDarkly.Api.Model.MembersBody](docs/MembersBody.md)
 - [LaunchDarkly.Api.Model.PatchComment](docs/PatchComment.md)
 - [LaunchDarkly.Api.Model.PatchOperation](docs/PatchOperation.md)
 - [LaunchDarkly.Api.Model.Policy](docs/Policy.md)
 - [LaunchDarkly.Api.Model.Prerequisite](docs/Prerequisite.md)
 - [LaunchDarkly.Api.Model.Project](docs/Project.md)
 - [LaunchDarkly.Api.Model.ProjectBody](docs/ProjectBody.md)
 - [LaunchDarkly.Api.Model.Projects](docs/Projects.md)
 - [LaunchDarkly.Api.Model.Role](docs/Role.md)
 - [LaunchDarkly.Api.Model.Rollout](docs/Rollout.md)
 - [LaunchDarkly.Api.Model.Rule](docs/Rule.md)
 - [LaunchDarkly.Api.Model.Site](docs/Site.md)
 - [LaunchDarkly.Api.Model.Statement](docs/Statement.md)
 - [LaunchDarkly.Api.Model.Statements](docs/Statements.md)
 - [LaunchDarkly.Api.Model.Stream](docs/Stream.md)
 - [LaunchDarkly.Api.Model.StreamBySDK](docs/StreamBySDK.md)
 - [LaunchDarkly.Api.Model.StreamBySDKLinks](docs/StreamBySDKLinks.md)
 - [LaunchDarkly.Api.Model.StreamBySDKLinksMetadata](docs/StreamBySDKLinksMetadata.md)
 - [LaunchDarkly.Api.Model.StreamLinks](docs/StreamLinks.md)
 - [LaunchDarkly.Api.Model.StreamSDKVersion](docs/StreamSDKVersion.md)
 - [LaunchDarkly.Api.Model.StreamSDKVersionData](docs/StreamSDKVersionData.md)
 - [LaunchDarkly.Api.Model.StreamUsageError](docs/StreamUsageError.md)
 - [LaunchDarkly.Api.Model.StreamUsageLinks](docs/StreamUsageLinks.md)
 - [LaunchDarkly.Api.Model.StreamUsageMetadata](docs/StreamUsageMetadata.md)
 - [LaunchDarkly.Api.Model.StreamUsageSeries](docs/StreamUsageSeries.md)
 - [LaunchDarkly.Api.Model.Streams](docs/Streams.md)
 - [LaunchDarkly.Api.Model.Target](docs/Target.md)
 - [LaunchDarkly.Api.Model.Usage](docs/Usage.md)
 - [LaunchDarkly.Api.Model.UsageError](docs/UsageError.md)
 - [LaunchDarkly.Api.Model.UsageLinks](docs/UsageLinks.md)
 - [LaunchDarkly.Api.Model.User](docs/User.md)
 - [LaunchDarkly.Api.Model.UserFlagSetting](docs/UserFlagSetting.md)
 - [LaunchDarkly.Api.Model.UserFlagSettings](docs/UserFlagSettings.md)
 - [LaunchDarkly.Api.Model.UserRecord](docs/UserRecord.md)
 - [LaunchDarkly.Api.Model.UserSegment](docs/UserSegment.md)
 - [LaunchDarkly.Api.Model.UserSegmentBody](docs/UserSegmentBody.md)
 - [LaunchDarkly.Api.Model.UserSegmentRule](docs/UserSegmentRule.md)
 - [LaunchDarkly.Api.Model.UserSegments](docs/UserSegments.md)
 - [LaunchDarkly.Api.Model.UserSettingsBody](docs/UserSettingsBody.md)
 - [LaunchDarkly.Api.Model.Users](docs/Users.md)
 - [LaunchDarkly.Api.Model.Variation](docs/Variation.md)
 - [LaunchDarkly.Api.Model.Webhook](docs/Webhook.md)
 - [LaunchDarkly.Api.Model.WebhookBody](docs/WebhookBody.md)
 - [LaunchDarkly.Api.Model.Webhooks](docs/Webhooks.md)
 - [LaunchDarkly.Api.Model.WeightedVariation](docs/WeightedVariation.md)


<a name="documentation-for-authorization"></a>
## Documentation for Authorization

<a name="Token"></a>
### Token

- **Type**: API key
- **API key parameter name**: Authorization
- **Location**: HTTP header
