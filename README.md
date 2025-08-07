# FaceTec AAR

> 📦 Wrapper Android para o SDK `.aar` da [FaceTec](https://dev.facetec.com/), preparado como módulo reutilizável e versionado automaticamente com [semantic-release](https://semantic-release.gitbook.io/semantic-release/).

---

## 📘 Visão Geral

Este projeto encapsula o arquivo `.aar` da FaceTec como **uma bibioteca via Jitpack**. Ele permite que projetos Android ou React Native utilizem o SDK sem precisar manipular diretamente o `.aar`.

## 🚀 Como Usar em um Projeto

Com o pacote buildado e funcionando, na biblioteca da Aziface adicione o seguinte trecho de código em android/build.gradle:

// android/build.gradle

```groovy
repositories {
// ...
maven { url '<https://jitpack.io>' }
}
```

```groovy
dependencies {
// ...
implementation 'com.github.USER_GITHUB:REPOSITORY:LIBRARY_VERSION_IN_JITPACK'
}
```

### Pra finalizar, em seu app, adicione em `android/build.gradle` e `android/app/build.gradle` o seguinte repositório maven:

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

### FaceTec SDK Version: 9.7.47
