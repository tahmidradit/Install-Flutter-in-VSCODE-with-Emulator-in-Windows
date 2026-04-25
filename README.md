# Install-Flutter-in-VSCODE-with-Emulator-in-Windows
Required downloads:
1. Flutter SDK bundle ZIP file : https://docs.flutter.dev/install/manual
2. JDK 21 : https://www.oracle.com/apac/java/technologies/downloads/#jdk21-windows
3. Visual Studio Code : https://code.visualstudio.com/Download#
4. Android Command line tools : https://developer.android.com/studio

Choose a folder for your installation. I have choosen C:\src for installation having 2 folders Android and Flutter 
1. Extract Flutter SDK bundle ZIP file in C:\src\Flutter . <img width="115" height="72" alt="image" src="https://github.com/user-attachments/assets/72eda3f1-fb11-4d18-b2c3-d2442d2be6d4" />
Now Setup environment variable. Press Win + R, type sysdm.cpl
   <img width="411" height="469" alt="image" src="https://github.com/user-attachments/assets/56df35e2-55a1-4442-b986-1274f648ff93" />
Now double click on Path
<img width="616" height="584" alt="image" src="https://github.com/user-attachments/assets/145f90de-ba7f-4b27-a7b8-e313756581d8" />

Click new 

<img width="108" height="340" alt="image" src="https://github.com/user-attachments/assets/11941fdb-abae-4abc-892a-83a13d0ccae0" />

Paste C:\src\Flutterflutter\bin to your environment variables. Enter flutter --version to check the installation.

2. Install JDK 21 and add C:\Program Files\Java\jdk-21\bin to your path. Enter java --version to check the installation.
3. Extract Android Command line tools in C:\src\Android\SDK and make a new folder named "latest" and move everything inside cmdline-tools in latest folder. Now add  C:\src\Android\SDK\cmdline-tools\latest\bin in your environment variables path.
4. Open cmd and enter the command: sdkmanager --list and see the list of tools you need to download. You need to install build tools, platform, system images of google_apis_playstore 64 Bit from the list. Always choose the versions of build tools and platform the latest stable. Try to use the final version like build tool 37, not the rc versions like 37 rc. and it's better to use android 9 to test the app compitability in older versions of android. Because this is sure that all android user don't have the latest phones at all. So, test your app in older version of android, will work in latest also.
5. Now find out your versions from sdkmanager --list you want to install and enter the command in cmd: sdkmanager "platform-tools" "build-tools;37.0.0" "platforms;android-37.0" "system-images;android-28;google_apis_playstore;x86_64"
6. Add C:\src\Android\SDK\platform-tools in the environment variables path. Do not test your app as web app in web browsers. Always test your app in emulator. So, enter the command flutter config --no-enable-windows-desktop 
7. Now enter the command flutter doctor . You may have remaining some licences to accept. Enter the command flutter doctor --android-licenses and enter y to accept licences.
8. Now again enter flutter doctor <img width="793" height="146" alt="image" src="https://github.com/user-attachments/assets/f0fc38bc-3962-4bbf-8af6-94accd7b3e14" />

   If you see • No issues found! message, you have syccessfully installed Android SDK and Flutter.
9. Open VS Code and install Flutter, Dart, Android iOS Emulator extentions.
10. Open Settings in vs code and search emulator . Paste C:\src\Android\SDK\emulator in Emulator Path and Emulator Path Windows.
11. Press Win + R, enter appwiz.cpl and click Turn Windows features on or off. Now Check Windows Hypervisor Platform and click OK. Reboot your pc when done.
12. Open cmd and enter: avdmanager create avd --name "Pixel" --package "system-images;android-28;google_apis_playstore;x86_64" --device "pixel_6" to create virtual device.
13. Open VS Code and Ctrl + Shift + P and type Emulator select or click emulator option. You will see your newly created Pixel device. Select Pixel and your virtual device will start.
14. You are ready to build android apps in Flutter. You don't need to install android studio anymore. You are all set. Start building your dream...!
    
   

    

