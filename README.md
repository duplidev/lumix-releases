# Lumix Releases
This repository hosts the lumix releases and its packages.

## Usage

Add to your `build.gradle.kts`:
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
