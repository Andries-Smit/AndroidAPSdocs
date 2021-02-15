# Handmatige installatie van Google Play-service voor Sony Smartwatch 3

De Sony Smartwatch 3 is een van de meest populaire horloges om mee te gebruiken AAPS. Helaas heeft Google de ondersteuning voor wear OS 1.5-apparaten laten vallen herfst 2020. Dit leidt tot problemen bij het gebruik van Sony SW3 met AndroidAPS 2.7 en hoger.

De volgende oplossing zou de tijd van de Sony Smartwatch 3 moeten verlengen kan worden gebruikt, maar houd er rekening mee dat het nodig is om over te schakelen naar een nieuwe smartwatch zal vroeg of laat komen.

## 1. Download the latest GService for Wear OS

- Using [apkmirror website](https://www.apkmirror.com/apk/google-inc/google-play-services-android-wear/) you can find the latest apk for "Google Play Services (Wear OS)".

  > Architecture: armeabi-v7a, Minimum Version: Android 6.0+, Screen DPI: nodpi

- You must ensure 2 things:

  - Is it the latest version?
  - Is it compatible with Android 6.0+ (as it's the wear android version, 7.0+ and above will not work)?

- Sooner or later, Google will definitely drop Android 6.0. When this will happen, the latest version will not be available anymore for Android 6.0+, therefore it will be the end.

## 2. Download/Install adb debugging tools on your computer

- There are multiple ways to install the adb debugging tool.
- It is recommended to use [SDK Platform Tools](https://developer.android.com/studio/releases/platform-tools): Just download zip file and unzip to a directory of your choice.

## 3. Enable ADB Debugging options on your watch

- Enable developer mode by going to Settings --&gt; About --&gt; Build number
- Click it 7 times.
- Now go to Settings --&gt; Developer Options --&gt; ADB Debugging (enable)

## 4. Connect your watch to your computer

- Then plug your smartwatch to PC.
- Rename latest downloaded google services APK using some short and simple name (let's say SW3fix.apk).
- Place this APK to the directory of your adb tool (in our case: the directory of unzipped SDK Platform Tools).
- Open Windows terminal using command „cmd“ in Windows start menu.
- In terminal, go to the directory that includes your adb tool and google services APK (type command „cd \[your path\]“, e.g. „cd C:UsersSWR50loopersdktools“).
- Then type “adb devices”.
- After a moment, you should get a prompt asking for debugging permission on your watch: accept.
- In the terminal, you should now see something like "14452D11F536B52 device" when typing "adb devices" again.
- If you see "unauthorized" or else, you're not ready for the next step, go back and try again.
- If you struggle at this step, you may need specific drivers or else for your watch. Google will be your best friend at this point.
- Then wait, the installation can take several minutes.

## 5. Send the app to your watch

- In terminal enter this command „adb install -r -g aplicationname.apk“ (so in our case „adb install -r -g SW3fix.apk“).

  ![Terminal command](../images/SonySW3_Terminal1.png)

- Wait for about 4–5 minutes for installation to complete.

  ![Terminal successful installation](../images/SonySW3_Terminal2.png)

- Once it's done, restart your watch and you should see the apps beginning to synchronize themself promptly.
