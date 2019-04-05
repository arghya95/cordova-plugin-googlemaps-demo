## cordova-plugin-googlemaps-demo
cordova google maps plugin v2 and its implementation installation steps of this plugin for ionic framework

```
npm install @ionic-native/core@4.18.0 @ionic-native/google-maps@4.21.0 
```

and then 

```
ionic cordova plugin add cordova-plugin-googlemaps --variable API_KEY_FOR_ANDROID="..." --variable API_KEY_FOR_IOS="..." 
```

use your api key for android and ios from.To generate api key visit https://console.developers.google.com/projectselector/apis/library

In this repository I use cordova plugin googlemaps verison 2.5.3 and @ionic-native/google-maps version 4.21.0.


## For iOS
now you have to build ios.If it fails then
perform following changes 

````
ionic cordova platform add ios
cd platforms/ios
pod setup
pod install
cd ../../
ionic cordova run ios
````

## For Android
now you have to build for android.if it fails then

perform following changes in platforms/android/project.properties and build.gradle

Here is the details

project.properties

```
target=android-26 
android.library.reference.1=CordovaLib 
android.library.reference.2=app cordova.gradle.include.1=cordova-plugin-googlemaps/starter-tbxml-android.gradle
cordova.system.library.1=com.google.android.gms:play-services-maps:15.0.1
cordova.system.library.2=com.google.android.gms:play-services-location:15.0.1
cordova.system.library.3=com.android.support:support-core-utils:27.+
```

and build.gradle
```
dependencies { 
    implementation fileTree(dir: 'libs', include: '*.jar') // SUB-PROJECT DEPENDENCIES START 
    implementation(project(path: ":CordovaLib")) 
    compile "com.google.android.gms:play-services-maps:15.0.1" 
    compile "com.google.android.gms:play-services-location:15.0.1" 
    compile "com.android.support:support-core-utils:27.+" // SUB-PROJECT DEPENDENCIES END 
}
```
If others files are missing ignore those.Perform changes whatever you have in your project.

For more details visit https://docs.google.com/presentation/d/e/2PACX-1vScoho1ensbR4qCI9AIuQN55BZVvK73pAjI7sumDvW3CrxxHnrmpXWUjx2-8CpFibqU1EjLKCRhuthJ/pub?start=false&loop=false&delayms=3000&slide=id.g282d0a7bfd_0_107

Thanks....
