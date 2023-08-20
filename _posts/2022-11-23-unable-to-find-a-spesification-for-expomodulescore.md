---
title: "Unable to find a spesification for ExpoModulesCore"
excerpt: "When you build apps for iOS using React Native, sometimes you will encounter problems while running the build, one of them is that you don't find the ExpoModulesCore package as shown below."
share: true
comments: true
header:
  image: /assets/images/expo.webp
  teaser: /assets/images/expo.webp
  overlay_image: /assets/images/unsplash-image-2.jpg
  og_image: /assets/images/expo.webp
categories:
  - ReactNative
tags:
  - React Native
  - iOS
  - Expo
image: /assets/images/expo.webp
---

When you build apps for iOS using React Native, sometimes you will encounter problems while running the build, one of them is that you don't find the ExpoModulesCore package as shown below.

This error occurs because the expomodulescore version in the pod is not available with the same version used in package.json. So below I will list the steps I took to deal with this error.
1. Because in case we using using react-native version 0.64.4, so change or add expo-modules-core version to **^0.6.5** on your package.json <code>"expo-modules-core": ^0.6.5</code>
2. Delete node_modules folder in project root
3. Delete *yarn.lock* and *package-lock.json* if exist in project root
4. Install JS Package using yarn (don't using NPM because sometimes making error) **yarn install** and make sure your yarn version 1.22.x above.
5. Synchronize package.json with pods in folder _ios_ using command **pod deintegrate** and **pod install**.
6.  Run command **npx install-expo-modules** in root project to installing expo-modules on node_modules and pod.
7.  then, try to run iOS app using **yarn run ios**.