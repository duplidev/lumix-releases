# Lumix Releases
This repository hosts the lumix releases and its packages.

![version](https://img.shields.io/github/v/release/duplidev/lumix-releases)

## Usage

Add this to your `build.gradle.kts` and replace `\<version\>` with the current release.
```kotlin
repositories {
    maven {
        url = uri("https://maven.pkg.github.com/duplidev/lumix-releases")
    }
}

dependencies {
    implementation("dev.duplicat:api:<version>")
}
```
