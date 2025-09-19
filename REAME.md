Explanation of the Workflow

- Trigger: The workflow triggers on a push to the ```dev``` branch
- Job: The ```build``` job runs on an ```ubuntu-latest``` runner
- Steps:
  - Checkout: Uses the ```actions/checkout``` action to check out the repository
  - Set up JDK: Uses the ```actions/setup-java``` action to set up JDK 11
  - Grant permission: Grants execute permission to the ```gradlew``` script
  - Build: Runs the Gradle build command to build the project
  - Sign APK: Uses environment variables stored in GitHub secrets to sign the APK
  - Upload APK: Uses the ```actions/upload-artifact``` action to upload the signed APK as a build artifact