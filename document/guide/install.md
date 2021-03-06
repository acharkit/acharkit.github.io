---
layout: page
title: install
permalink: /document/guide/install
menu: false
---

## Install

#### Install from AAR

For use acharkit must be [download](https://github.com/acharkit/acharkit-android/releases) last version.

Acharkit support androidx and google appcompat

After adding aar to the lib folder in the project must be added the line below to build.gradle in the project root

***

```groovy
allprojects {
        repositories {
            google()
            jcenter()
            flatDir {
                dirs 'libs'
            }
        }
    }
```

***

And add the line below to gradle.build module (such as app , ....)

```groovy

    implementation(name:'acharkit-release-x.x.x', ext:'aar')
    or
    compile(name:'acharkit-release-x.x.x', ext:'aar')

```

***

If using androidx

Note: Support androidx from version 0.1.1 to later

```groovy

    implementation(name:'acharkitx-release-x.x.x', ext:'aar')
    or
    compile(name:'acharkitx-release-x.x.x', ext:'aar')

```
