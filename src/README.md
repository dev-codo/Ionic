https://www.youtube.com/watch?v=CYNZ6QTbB3A
Nov 23, 2018
start at 17:40

# Install ionic globally
npm install -g ionic

# Install Cordova globally
npm install -g cordova

# Create a project
ionic start <name_of_project> blank|tabs|... --type=angular (for ionic 4)
ionic start <name_of_project> blank|tabs|... --type=ionic-angular (for ionic 3)

# Run
ionic serve

# Run in ionic lab mode
ionic serve -l

# Add IOS, Android & browser platforms
ionic cordova platform add android | ionic cordova platform add ios | ionic cordova platform add browser

# (if) remove any platform
ionic cordova platform rm <OS>

# Run application on browser | android | ios
ionic cordova emulate browser | ionic cordova emulate ios --list (to check devices available)

# Run on Android
ionic cordova run android (or just 'cordova run android --verbose --info)

# Install android-sdk
(on '/'): sudo apt install default-jdk
...
ignore the 'export paths', consider the below one
https://stackoverflow.com/a/53508177/9242930

# Accept SDK license agreements
(android-sdk/tools/bin): ./sdkmanager --licenses

# Create Build tools / "Install the Android build tools version 19.1.0 or higher"
sdkmanager "platform-tools" "platforms;android-28"
sdkmanager "build-tools;28.0.0"
export ANDROID_HOME=/<installation location>/android-sdk (<installation location> : /usr/mingau/android-sdk)
export PATH=${PATH}:$ANDROID_HOME/tools:$ANDROID_HOME/platform-tools
https://stackoverflow.com/questions/31190355/ionic-build-android-error-no-installed-build-tools-found-please-install-the
https://stackoverflow.com/questions/43029394/gradle-sync-failed-no-installed-build-tools-found-install-the-android-build-t/43362671

# Create systems-images (for emulator) - AVD (./avdmanager)
 ./sdkmanager "system-images;android-27;google_apis_playstore;x86"
 ./avdmanager create avd --force --name -testAVD --abi google_apis/x86_64 --package 'system-images;android-27;google_apis_playstore;x86'
 ./avdmanager create avd -n test -k "system-images;android-23;google_apis;x86" -b x86 -c 100M -d 7 -f
 ./avdmanager list avd
 https://stackoverflow.com/questions/43275238/how-to-set-system-images-path-when-creating-an-android-avd 
 https://stackoverflow.com/questions/42792947/how-to-create-android-virtual-device-with-command-line-and-avdmanager





