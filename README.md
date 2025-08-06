# facetec-aar

> 📦 Wrapper Android para o SDK `.aar` da [FaceTec](https://dev.facetec.com/), preparado como módulo reutilizável e versionado automaticamente com [semantic-release](https://semantic-release.gitbook.io/semantic-release/).

---

## 📘 Visão Geral

Este projeto encapsula o arquivo `.aar` da FaceTec como um **módulo Android via Maven**. Ele permite que projetos Android ou React Native utilizem o SDK sem precisar manipular diretamente o `.aar`.

Principais recursos:

- ✅ Integração fácil via Git Submodule
- ✅ Versionamento automático via semantic-release
- ✅ Sem publicação no npm

## 🚀 Como Usar em um Projeto

### ✅ Pré-requisitos

- Projeto Android ou React Native com suporte a múltiplos módulos
- Git com submodules habilitado

### 📥 Adicionando como Submódulo

```bash
git submodule add git@github.com:azifydev/facetec-aar.git libs/facetec-aar
```

## ⚙️ Configuração no Gradle

settings.gradle:

```groovy
include ':facetec'
project(':facetec').projectDir = new File(rootDir, 'libs/facetec-aar/facetec')
```

build.gradle:

```groovy
allprojects {
    repositories {
        maven {
            url uri('external/facetec-aar/build/repo')
        }
        google()
        mavenCentral()
    }
}

```

app/build.gradle:

```groovy
dependencies {
    implementation 'com.azify.facetec:facetec-sdk:9.7.47'
}

```

## 🧬 Clonagem com Submódulo

```bash
git clone --recurse-submodules git@github.com:azifydev/facetec-aar.git
```

ou caso já tenha clonado:

```bash
git submodule update --init --recursive
```

## 📦 Versionamento Automático

#### Este repositório utiliza o semantic-release para gerenciar versões, changelogs e GitHub Releases com base em mensagens de commit semânticas.

### 🔧 Configuração

- Releases automáticos na branch main

- Tags no formato vX.Y.Z

- Atualização do CHANGELOG.md

- Versão do package.json também atualizada (sem publicação no npm)

### 📝 Exemplo de mensagens válidas de Commit:

```
feat: adiciona suporte ao novo build do SDK
```

```
fix: adiciona correção de segurança
```

```
chore: atualiza dependências do Gradle
```

## 🧰 Manutenção

##### SDK atualmente integrado: FaceTec 9.7.47

[![Release](https://img.shields.io/github/v/release/azifydev/facetec-aar?label=vers%C3%A3o&style=flat-square)](https://github.com/azifydev/facetec-aar/releases)
[![Build](https://img.shields.io/github/actions/workflow/status/azifydev/facetec-aar/release.yml?label=build&style=flat-square)](https://github.com/azifydev/facetec-aar/actions)
[![Last Commit](https://img.shields.io/github/last-commit/azifydev/facetec-aar?style=flat-square)](https://github.com/azifydev/facetec-aar/commits/main)
[![License](https://img.shields.io/badge/license-private-red?style=flat-square)](#)
