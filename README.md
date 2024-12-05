# Expo ImagePicker Custom Camera URI Issue

This repository demonstrates a bug encountered when using Expo's ImagePicker with a custom camera implementation. The ImagePicker returns a response, but the image URI is inaccessible, leading to errors or null values.

## Bug Description

The problem occurs when using `ImagePicker.launchCameraAsync()` with a custom camera.  The result object seems correct, but attempting to access `result.uri` often yields an inaccessible or invalid URI.  This is likely caused by a conflict in image processing between the custom camera and the ImagePicker library.

## Solution

The solution involves ensuring both the custom camera and the ImagePicker use a consistent method for handling and storing image data. The example provided synchronizes image saving using the `Camera.takePictureAsync` method's `uri` parameter, which is then correctly handled by `ImagePicker`.