# ForgeGradle 6 for Minecraft 1.7.10

Fork of [ForgeGradle](https://github.com/MinecraftForge/ForgeGradle) with support for Minecraft 1.7.10.

## Changes from upstream

- Handle `userdev3` classifier (legacy format for 1.7.10)
- Fix inject source handling when MCP config lacks inject prefix
- Support empty inject folders (1.7.10 case)
- Fallback to parent patcher inject when MCP inject is null

## Installation

### Option A: Use pre-built artifacts (recommended)

Download the release archive from [Releases](https://github.com/roggy666/ForgeGradle-6-for-1.7.10/releases) and follow the instructions in `README.md`.

### Option B: Build from source

```bash
git clone https://github.com/roggy666/ForgeGradle-6-for-1.7.10.git
cd ForgeGradle-6-for-1.7.10
git checkout FG_6.0
./gradlew publishToMavenLocal
```

## Usage

In `build.gradle.kts`:

```kotlin
plugins {
    id("net.minecraftforge.gradle") version "0.0.0"
}

minecraft {
    mappings("snapshot", "20140925-1.7.10")
}

dependencies {
    minecraft("net.minecraftforge:forge:1.7.10-10.13.4.1614-1.7.10:userdev3")
}
```

## Requirements

- Java 8 (required for Minecraft 1.7.10)
- Gradle 8.x

## Technical Notes

- Uses `userdev3` classifier (legacy format for 1.7.10)
- MCP mappings: `snapshot_20140925`
- Forge version: `10.13.4.1614`

## Credits

Based on [ForgeGradle](https://github.com/MinecraftForge/ForgeGradle) by MinecraftForge team.
