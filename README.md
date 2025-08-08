# FaceTec AAR

![JitPack](https://img.shields.io/jitpack/version/com.github.azifydev/facetec-aar?style=flat&color=brightgreen&link=https%3A%2F%2Fjitpack.io%2F%23azifydev%2Ffacetec-aar)

> 📦 Android wrapper for [FaceTec](https://dev.facetec.com/) `.aar` SDK, prepared as a reusable module and automatically versioned with [semantic-release](https://semantic-release.gitbook.io/semantic-release/).

---

## 📘 Overview

This project encapsulates the FaceTec `.aar` file as **a library via Jitpack**. It allows Android or React Native projects to use the SDK without needing to directly manipulate the `.aar` file.

## 🚀 How to use?

With the package built and working, in the your app/library add the following code snippet to `android/build.gradle`:

```groovy
// android/build.gradle
repositories {
  // ...
  maven { url 'https://jitpack.io' }
}
```

```groovy
dependencies {
  // ...
  implementation 'com.github.azifydev:facetec-aar:{{version}}'
}
```

To finish, in your app, add the following `maven` repository to `android/build.gradle` and `android/app/build.gradle`:

```groovy
// android/build.gradle
buildscript {
  // ...
  repositories {
    // ...
    maven { url 'https://jitpack.io' }
 }
}
```

```groovy
// android/app/build.gradle
repositories {
  // ...
  maven { url 'https://jitpack.io' }
}
```
