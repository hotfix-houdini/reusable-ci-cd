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

 **See the Examples folder for actual exmaples of using these workflows from my own repos.**

# Adding Docker Publish support to a .net Project
Add this to your CS Proj file:
```xml
<PropertyGroup>
	<IsPublishable>true</IsPublishable>
	<EnableSdkContainerSupport>true</EnableSdkContainerSupport>
</PropertyGroup>
```

# Developer Workflow
1. branch and make the desired changes.
2. in a client repo, target the @branch version of the workflow and verify functionality.
3. merge into mainline
4. run `cd-tag-repo` with the appropriate tag version so clients can start using it, being cognizant of semantic versioning.
