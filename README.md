# Lumix Releases
This repository hosts the lumix releases and its packages.

![version](https://img.shields.io/github/v/release/duplidev/lumix-releases)

## Usage

1. **Generate a GitHub Token:** Create a [Personal access token (classic)](https://github.com/settings/tokens) with the `read:packages` scope.
2. **Configure Credentials:** Add the following to your local `gradle.properties` file, located at `~/.gradle/gradle.properties`:

   ```properties
   gpr.user=USERNAME
   gpr.key=TOKEN
   ```

3. **Setup Gradle:** Add this to your `build.gradle.kts` and replace `<version>` with the current release:
```kotlin
repositories {
    maven {
        url = uri("https://maven.pkg.github.com/duplidev/lumix-releases")
        credentials {
            username = project.findProperty("gpr.user") as String? ?: System.getenv("USERNAME")
            password = project.findProperty("gpr.key") as String? ?: System.getenv("TOKEN")
        }
    }
}

dependencies {
    implementation("dev.duplicat:api:<version>")
}
```
