# Install-Flutter-in-VSCODE-with-Emulator-in-Windows
Required downloads:
1. Flutter SDK bundle ZIP file : https://docs.flutter.dev/install/manual
2. JDK 21 : https://www.oracle.com/apac/java/technologies/downloads/#jdk21-windows
3. Visual Studio Code : https://code.visualstudio.com/Download#
4. Android Command line tools : https://developer.android.com/studio

Choose a folder for your installation. For example make C:\src for installation having 2 folders Android and Flutter 
## 1. Extract Flutter SDK bundle ZIP file 
> C:\src\Flutter
<img width="115" height="72" alt="image" src="https://github.com/user-attachments/assets/72eda3f1-fb11-4d18-b2c3-d2442d2be6d4" />

### Setup Environment Variable Path 

> ⊞ Win + R, type sysdm.cpl and click OK

   <img width="411" height="469" alt="image" src="https://github.com/user-attachments/assets/56df35e2-55a1-4442-b986-1274f648ff93" />
   
Double click on Path

  <img width="616" height="584" alt="image" src="https://github.com/user-attachments/assets/145f90de-ba7f-4b27-a7b8-e313756581d8" />


Click new 
 
  <img width="108" height="340" alt="image" src="https://github.com/user-attachments/assets/11941fdb-abae-4abc-892a-83a13d0ccae0" />


## Setup Environment Variable Path
> add C:\src\Flutter\flutter\bin 
### Verify 
> flutter --version  

## 2. JDK 21 Installation 
Run setup file
## Setup Environment Variable Path 
> C:\Program Files\Java\jdk-21\bin .
### Verify 
> java --version
## 3. Android SDK Installation 
Extract Command line tools in the following directory.
> C:\src\Android\SDK
Make a new folder named "latest" and move everything inside cmdline-tools in latest folder.
## Setup Environment Variable Path 
> C:\src\Android\SDK\cmdline-tools\latest\bin
## SDK Manager 
> sdkmanager --list
Enter the above command to see the list of tools you need to download. You need to install build tools, platform, system images of google_apis_playstore 64 Bit from the list. Always choose the latest stable versions of build tools and platform tools. Try to use the latest versions like build tool 37, not the rc versions like 37rc and it's better to use older android versions like android 9 to test the app compitability in older versions of androids. Because all of your app users mayn't have the latest phones at all. So, test your app in older version of android, will work in latest also.
## Download Build tools, Platform tools, System images for the emulator
Enter the command
> sdkmanager "platform-tools" "build-tools;37.0.0" "platforms;android-37.0" "system-images;android-28;google_apis_playstore;x86_64"
## Setup Environment Variable Path
C:\src\Android\SDK\platform-tools  
## Disable Windows Desktop Development in Flutter
Do not test your app as web app in web browsers. Always test your app in emulator. So, disable windows desktop development in Flutter to avoid unnecessary warning in flutter doctor.
> flutter config --no-enable-windows-desktop
### Flutter Doctor
Check your installation may have remaining left to complete some actions. Enter the command to check what you have to do more.
> flutter doctor
## Accept Licenses
Accept all licences and enter all y in the license agreement  
> flutter doctor --android-licenses
ENTER FLUTTER DOCTOR AGAIN. 
<img width="793" height="146" alt="image" src="https://github.com/user-attachments/assets/f0fc38bc-3962-4bbf-8af6-94accd7b3e14" />

If you see • No issues found! message, you have syccessfully installed Android SDK and Flutter.

### Visual Studio Code Setup 
Install Required extentions : Flutter, Dart, Android iOS Emulator

11. Open Settings in vs code and search emulator . Paste C:\src\Android\SDK\emulator in Emulator Path and Emulator Path Windows.
12. Press Win + R, enter appwiz.cpl and click Turn Windows features on or off. Now Check Windows Hypervisor Platform and click OK. Reboot your pc when done.
13. Open cmd and enter: avdmanager create avd --name "Pixel" --package "system-images;android-28;google_apis_playstore;x86_64" --device "pixel_6" to create virtual device.
14. Open VS Code and Ctrl + Shift + P and type Emulator select or click emulator option. You will see your newly created Pixel device. Select Pixel and your virtual device will start.
15. You are ready to build android apps in Flutter. You don't need to install android studio anymore. You are all set. Start building your dream...!
    
   

    

