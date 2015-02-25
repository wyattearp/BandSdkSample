Microsoft Band SDK Preview README

1. LICENSE

Use of the Microsoft Band SDK is granted under the terms of the license
agreement found at http://go.microsoft.com/fwlink/?LinkID=525148.


2. CONTENTS

The Microsoft Band SDK Preview for Android package contains the following:

BandSdkSample – a sample Android application that shows how to use the Microsoft Band SDK.

microsoft-band-{version}.jar – the Java jar library for the Microsoft Band SDK
                               Preview. The file name contains the version of
                               the SDK release.

readme.txt – this file.


3. PREREQUISITES

The Microsoft Band SDK Preview requires the latest version of the Microsoft
Health application installed (version 1.3.10217.2 or newer), as well as having
the Band updated with the latest firmware (done through the Health application).


4. INSTALLATION INSTRUCTIONS

NOTE: the minimum supported Android API version is 17.

First, include the Microsoft Band SDK jar file in your Android project.  To do
that in Android Studio:
- Go to your Android project's application directory and locate the libs
  folders (you can create it if it does not already exist), and copy the jar
  file to this location.
- Open the Project Structure window from the File menu
- Select the application module from the Modules list on the left
- Select the Dependencies tab on the right
- Click the + button on the right and select File dependency
- Expand the libs folder, select the jar file, and click OK

In addition to adding the jar file to your Android project, you will also need
to declare the following uses-permission tags in the AndroidManifest.xml:
   <uses-permission android:name="android.permission.BLUETOOTH"/>
   <uses-permission android:name="com.microsoft.band.service.access.BIND_BAND_SERVICE"/>


5. SUPPORT AND FEEDBACK

For questions and support use stackoverflow.com with the tag 'msband'.

For feedback, such as feature requests and bug reports, please send e-mail
to msbandsdk@microsoft.com.


6. KNOWN ISSUES

  1) If you are compiling against version 21 of the Android SDK and the
     target SDK version in your manifest is set to 21, the BandClient's connect
     method will fail on devices running Lollipop. The fix for this issue
     is to use the following uses-sdk tag in the AndroidManifest.xml:
     <uses-sdk android:minSdkVersion="17" android:targetSdkVersion="19" />

  2) Microsoft Health must always be installed before an application that
     uses this SDK or else BandClient's connect method will always fail.