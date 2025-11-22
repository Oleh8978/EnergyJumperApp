1. copy all files to EnergyJumperApp/www/

2. run commands 

cordova build android
cordova run android --device

make a build 

# my-release-key.jks, alias_name, і password
keytool -genkey -v -keystore my-release-key.jks -keyalg RSA -keysize 2048 -validity 10000 -alias alias_name

APK
cordova build android --release

sign apk file 
jarsigner -verbose -sigalg SHA1withRSA -digestalg SHA1 -keystore /path/to/my-release-key.jks platforms/android/app/build/outputs/apk/release/app-release-unsigned.apk alias_name


aab file:

cordova build android --release -- --packageType=bundle

output dir:

platforms/android/app/build/outputs/bundle/release/app-release.aab


local tests 

adb install -r platforms/android/app/build/outputs/apk/release/app-release-unsigned.apk
