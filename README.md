# Renovate Bot Gradle build minimal repo
Minimal repo for Renovate Bot [issue 13251](https://github.com/renovatebot/renovate/issues/13251).

## Expected Behaviour

Renovate bot should update two files with the same Gradle version:
`./gradle/wrapper/gradle-wrapper.properties`, which is already handled correctly, and `build.gradle`, which should have its wrapper task updated.

```
wrapper {
    gradleVersion = "7.1.1"
    distributionType = "ALL"
}
```

This is a Gradle task for installing the wrapper.
It's often used in projects and CI for making sure the wrapper is always correctly.
Many people also don't use it.
If it's present, it should have the same version upgrade as in `gradle-wrapper.properties`.
The property `distributionType` isn't required, but should be preserved.

The task can be tested with `./gradlew wrapper`.
