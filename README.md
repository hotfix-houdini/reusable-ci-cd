# Included workflows
- reusable-dotnet-ci
  - includes docker permissions for TestContainer test support
- reusable-dotnet-cd-image
  - uses .net 8's docker integration
  - publishes to an Azure Container Registry
- reusable-dotnet-cd-nuget
  - a user manually provides a version, e.g. `1.0.0`
  - includes CI steps
  - tags the repo with the provided version
  - publish to either nuget.org or an internal nuget feed with the same version
  - creates a release on the repo, optionally providing a release body from a markdown file in the repo.

# Adding Docker Publish support to a .net Project
Add this to your CS Proj file:
```xml
<PropertyGroup>
	<IsPublishable>true</IsPublishable>
	<EnableSdkContainerSupport>true</EnableSdkContainerSupport>
</PropertyGroup>
```
