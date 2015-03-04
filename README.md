# springer-gocd-cloudfoundry-plugin
Go plugin for detecting application version in Cloud Foundry.

Status: Version 1.0.2 released.  Binary distribution jar now available for each release.

## Potential use cases
* Execution of tests that don't need to block a deploy.
* Deploy of an application that needs to match the version of the other application - e.g. an application providing preview functionality for CMS managed content.
* Performance testing - keep a record of the app over time without having to hook these tests into the application's build pipeline.

## Requirements
JDK 6 or higher.  Future versions may jump to 8+, but for now we'll stay aligned with Go CD.

## Building
./gradlew clean build

## Installing
After building, copy the generated jar file from build/libs/springer-gocd-cloudfoundry-plugin-1.0.jar to your Go server's external plugins directory.

Restart Go server to allow it to detect and install the new plugin.

Verify that the plugin has successfully been installed by navigating to the Admin / Plugins section on your Go server.

## Usage
There are two stages involved in making use of this Material:
  * Admin / Package Repositories
     Add Package Repository - select Cloud Foundry as the type and provide the credentials for accessing your Cloud Foundry
  * During pipeline creation, specify Package as Material type and select the repository that you created in the previous step
     Select Define New and provide the details of your app.

## Version History
1.0.2

23 February 2015

Revision number parsing updated to support positive real numbers.

1.0.1

22 February 2015

Password property 'secure'.

1.0.0

18 February 2015

Original release.

