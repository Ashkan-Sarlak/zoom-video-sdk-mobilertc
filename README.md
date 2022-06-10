# Purpose

This is a repository for sole purpose of installing *mobilertc.aar* to [jitpack](https://jitpack.io) instead of mavenLocal.

# Usage

    rootProject.allprojects {
        repositories {
            ...
            mavenLocal()                          <-- With local installation
            maven { url 'https://jitpack.io' }    <-- With jitpack installation
        }
    }

    dependencies {
        ...
        implementation 'us.zoom.sdk:mobilertc:1.0'                                 <-- Reference mobilertc from local installation
        implementation 'com.github.Ashkan-Sarlak:zoom-video-sdk-mobilertc:1.0'     <-- Reference mobilertc from jitpack
        
        // dependencies of mobiletrc SDK
        implementation 'androidx.security:security-crypto:1.1.0-alpha03'
        implementation 'com.google.crypto.tink:tink-android:1.5.0'
        implementation 'androidx.appcompat:appcompat:1.3.0'
        // end of dependencies of mobiletrc SDK
    }


# Notes

### Command used for installing the aar file in local maven
> mvn install:install-file -Dfile=path/to/mobilertc.aar -DgroupId=us.zoom.sdk -DartifactId=mobilertc -Dversion=1.0 -Dpackaging=aar

### User of this aar file
This mobilertc.aar file is identical to https://github.com/Ashkan-Sarlak/zoom_video_sdk/blob/master/android/mobilertc/mobilertc.aar

But that file is not being used there at all, it is possible to delete it from there; We keep it for now as a reference.

# Reference

https://medium.com/student-beans/publishing-a-library-as-a-aar-package-55ed725fa638

https://stackoverflow.com/questions/54838606/how-to-serve-aar-files-using-jitpack

https://github.com/AndroidDeveloperLB/SdkTest
