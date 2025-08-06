# FaceTec AAR

> 📦 Android wrapper for the [FaceTec](https://dev.facetec.com/) `.aar` SDK, prepared as a reusable module and automatically versioned with [semantic-release](https://semantic-release.gitbook.io/semantic-release/).

---

## 📘 Overview

This project encapsulates the FaceTec `.aar` file as an **Android module via Maven**. It allows Android or React Native projects to use the SDK without needing to directly manipulate the `.aar`.

Key features:

- ✅ Easy integration via Git Submodule
- ✅ Automatic versioning via `semantic-release`

## 🚀 How to Use in a Project

### ✅ Prerequisites

- Android or React Native project with multi-module support
- Git with submodules enabled

### 📥 Adding as Submodule

```bash
git submodule add git@github.com:azifydev/facetec-aar.git external/facetec-aar
```

A folder called `external` will be created in your project. Inside it, there will be another folder called `facetec-aar`, which contains the extracted contents of the FaceTec `.aar` file.

## ⚙️ Gradle Configuration

`build.gradle`:

```groovy
repositories {
    // ...
    maven {
        url = uri("../external/facetec-aar/build/repo")
    }
    google()
    mavenCentral()
    mavenLocal()
}

// ...

dependencies {
    // ...
    implementation 'com.azify.facetec:facetec-sdk:9.7.47'
}
```

## 🧬 Cloning with Submodule

```bash
git clone --recurse-submodules git@github.com:azifydev/facetec-aar.git
```

or if you have already cloned:

```bash
git submodule update --init --recursive
```

## ⚙️ Troubleshooting

### Build error when external isn't found

In some cases, the external directory isn't found during build. To resolve this error, you must add `mavenLocal()` to your `build.gradle` repositories block.

`build.gradle`:

```groovy
repositories {
    // ...
    mavenLocal()
}
```

`app/build.gradle`:

```groovy
repositories {
    // ...
    mavenLocal()
}
```

In other cases, the `build` folder inside `external/facetec-aar` wasn't generated. For generate this folder, inside `external/facetec-aar` run this command:

```bash
gradle publish
```

If you haven't gradle installed, install it using this command:

```bash
brew install gradle

# Use this command to check if it was installed
gradle -v
```

### Git submodule doesn't updated

Your external folder sometimes doesn't reflect updates when the submodule is updated. To fix this problem, run:

```bash
git submodule update --recursive --remote --merge
```
