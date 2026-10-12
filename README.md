# Palbase for Android

The Android SDK of [Palbase](https://palbase.studio), as a Maven repository served by GitHub Pages:
`https://palgroup.github.io/palbase-android/` — compiled packages only; the SDK's source is not public.

```kotlin
// settings.gradle.kts
dependencyResolutionManagement {
    repositories {
        google()
        mavenCentral()
        exclusiveContent {
            forRepository { maven("https://palgroup.github.io/palbase-android/") }
            filter { includeGroup("studio.palbase") }
        }
    }
}

// app/build.gradle.kts
dependencies {
    implementation(platform("studio.palbase:palbase-bom:0.1.0"))
    implementation("studio.palbase:palbase")
    implementation("studio.palbase:palbase-flags") // and palbase-analytics, -realtime, -notify, -storage, -palbe
}
```

minSdk 26, Kotlin 2.2 or newer. Every file is signed; the public key is `KEYS`. Licence: the Palbase SDK License (`LICENSE`).
