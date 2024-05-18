# reusable-ci-cd

## Adding Docker Publish support to a .net Project
Add this to your CS Proj file:
```xml
<PropertyGroup>
	<IsPublishable>true</IsPublishable>
	<EnableSdkContainerSupport>true</EnableSdkContainerSupport>
</PropertyGroup>
```