# Lumix Releases
This repository hosts the lumix engine releases.

![version](https://img.shields.io/github/v/release/duplidev/lumix-releases)

## Download
Get the latest build from the [Releases](https://github.com/duplidev/lumix-releases/releases) page.

## Setting up your project
To get started with Lumix, your Gradle project needs the setup below. 

### 1. Lumix API
![api version](https://img.shields.io/maven-central/v/dev.duplicat/api)
- Include the Maven Central repository
```gradle
repositories {
    mavenCentral()
}
```

- Add the latest Lumix API dependency
```gradle
dependencies {
    implementation("dev.duplicat:api:<release>")
}
```

### 2. Setup Shadow
> [!NOTE]
> This step is required, because the engine builds your game by calling `shadowJar` in your project.

- Add the Shadow plugin
```gradle
plugins {
    id("com.gradleup.shadow") version "9.4.1"
}
```
- Configure the jar
```gradle
tasks.shadowJar {
    archiveBaseName.set("game")
    archiveClassifier.set("")
    archiveVersion.set("")

    manifest {
        attributes["Main-Class"] = "dev.duplicat.lumix.GameLauncher"
    }

    exclude("assets/**")

    mergeServiceFiles()
}
```
