# Included workflows
- dotnet-ci
  - includes docker permissions for TestContainer test support
- dotnet-cd-image
  - uses .net 8's docker integration
  - publishes to an Azure Container Registry

# Adding Docker Publish support to a .net Project
Add this to your CS Proj file:
```xml
<PropertyGroup>
	<IsPublishable>true</IsPublishable>
	<EnableSdkContainerSupport>true</EnableSdkContainerSupport>
</PropertyGroup>
```