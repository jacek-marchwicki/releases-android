# Layer Android Releases

This repository contains binary distributions of Android products released by [Layer](http://layer.com).

## Layer SDK

This repository contains releases of the Android SDK for interacting with the Layer communications cloud. It provides a simple, object oriented interface to the rich messaging capabilities provided by the platform.  See the [changelog](releases/com/layer/sdk/layer-sdk/CHANGELOG.md) for the latest version and updates.

In order to use the SDK you must be a registered developer with a provisioned application identifier and have configured a backend system to act as an identity provider for your client applications. All aspects of this setup are covered in detail in the [Layer Integration Guide](https://preview.layer.com/docs/integration).

### Installation

The Layer Android SDK can be installed directly into your application by importing a JAR from the filesystem or an AAR via Maven. Quick installation instructions are provided below for reference, but please refer to the [Layer Integration Guide](https://preview.layer.com/docs/integration) for full details and troubleshooting.

#### Maven Installation

The recommended path for installation on Android is via [Maven](http://maven.apache.org/). Maven is a software project management and comprehension tool. It is capable of managing a project's build configuration and dependencies from a central location. You can install the Layer SDK into your project via Maven by adding the following code to your project's `build.gradle` file:

```groovy
repositories {
    mavenCentral()
    maven { url 'https://github.com/layerhq/releases-android/raw/master/releases/' }
}


dependencies {
    compile 'com.layer.sdk:layer-sdk:0.7.10+'
    compile 'org.slf4j:slf4j-api:1.7.7+'
}
```

Once you have successfully built your project, proceed to the [Verifying SDK Configuration](#verifying-sdk-configuration) section below.

#### JAR Installation

If you wish to install the Layer Android SDK directly from a JAR binary, then download the latest JAR release from the [Github project](https://github.com/layerhq/releases-android/tree/master/releases/com/layer/sdk/layer-sdk) and complete the following steps:

1. Drag the JAR file into the /libs directory of your Android Studio application
Navigate to the JAR file in Android Studio navigatior, right click and select "Add As A Library..."
2. Navigate to your build.gradle file and ensure that you include the following:

```groovy
dependencies {
    compile fileTree(dir: 'libs', include: ['*.jar'])
    compile 'com.android.support:appcompat-v7:20.+'
    compile 'com.android.support:support-annotations:20.+'
    compile 'com.google.android.gms:play-services:5.+'
    compile 'org.slf4j:slf4j-api:1.7.7'
}
```
Once you have successfully built your project, proceed to the [Verifying SDK Configuration](#verifying-sdk-configuration) section below.

### Verifying SDK Configuration

Once you have finished installing the Layer SDK, you can test your configuration by connecting a client to the Layer cloud. To do so, edit your `Application` object's `onCreate()` method to include the code below (note that you must substitute the app ID placeholder text with your actual app identifier):

```java
// Instatiates a LayerClient object
UUID appID = UUID.fromString("INSERT-UUID-HERE")
LayerClient client = LayerClient.newInstance(this, appID, "GCM ID");

// Asks the LayerSDK to establish a network connection with the Layer service
client.connect();
```

Launch your application and verify that the connection is successful. You are now ready to begin authenticating clients and sending messages. Please refer to the [Layer Integration Guide](https://preview.layer.com/docs/integration) for details.

## Contact

You can reach the Layer team at any time by emailing [support@layer.com](mailto:support@layer.com).

## License

Layer SDK for Android is licensed under the [Layer SDK License](LICENSE.md).
