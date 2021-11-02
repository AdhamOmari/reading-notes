# Application Fundamentals


> Android apps can be written using Kotlin, Java, and C++ languages. The Android SDK tools compile your code along with any data and resource files into an APK or an Android App Bundle.

> An Android package, which is an archive file with an .apk suffix, contains the contents of an Android app that are required at runtime and it is the file that Android-powered devices use to install the app.

> Each Android app lives in its own security sandbox, protected by the following Android security features:


*  The Android operating system is a multi-user Linux system in which each app is a different user.
*  By default, the system assigns each app a unique Linux user ID (the ID is used only by the system and is unknown to the app). The system sets permissions for all the files in an app so that only the user ID assigned to that app can access them.

* Each process has its own virtual machine (VM), so an app's code runs in isolation from other apps.
  
* By default, every app runs in its own Linux process. The Android system starts the process when any of the app's components need to be executed, and then shuts down the process when it's no longer needed or when the system must recover memory for other apps.


> App components


> App components are the essential building blocks of an Android app. Each component is an entry point through which the system or a user can enter your app. Some components depend on others.

> There are four different types of app components:

* Activities
* Services
* Broadcast receivers
* Content providers

>  The manifest file

*Before the Android system can start an app component, the system must know that the component exists by reading the app's manifest file, AndroidManifest.xml. Your app must declare all its components in this file, which must be at the root of the app project directory.*

>The manifest does a number of things in addition to declaring the app's components, such as the following:

* Identifies any user permissions the app requires, such as Internet access or read-access to the user's contacts.
* Declares the minimum API Level required by the app, based on which APIs the app uses.
* Declares hardware and software features used or required by the app, such as a camera, bluetooth services, or a      multitouch screen.
* Declares API libraries the app needs to be linked against (other than the Android framework APIs), such as the Google Maps library