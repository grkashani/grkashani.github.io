[https://medium.com/@psyanite/how-to-add-app-launcher-icons-in-flutter-bd92b0e0873a]


How to add app launcher icons in Flutter
Neila
Neila
Follow
Feb 17, 2019 · 2 min read

It’s easy thanks to flutter_launcher_icons 💖
How it works
Here I will use NameMe as an example.

NameMe adaptive icon on Android
Three custom png files will be added to the project, and after updating pubspec.yaml and running the plugin, all remaining assets will be generated and automatically packaged when executing flutter run or flutter build.
I would highly recommend using Illustrator to create your assets, and use 900x900. For more information on how to create an Android adaptive icon see this article by Nick, it includes Bjango templates which you may find useful. See the NameMe Android Illustrator file and iOS template.
Instructions
First create a background.png and a foreground.png file for an Android adaptive icon, see examples and test your assets at Adapticon.

Android assets
2. Then create a single icon.png for iOS and fallback for Android, I think I’ve made mine wrong, please try using this template. I would recommend one Android fallback icon (with drop shadow) and follow the template for the iOS one.

iOS asset
3. Add the three png files into a folder (I chose assets/launcher/)
4. Edit pubspec.yaml
dev_dependencies: 
  flutter_launcher_icons: "^0.7.0"
flutter_icons:
  ios: true
  android: true
  image_path_ios: "assets/launcher/icon.png"
  image_path_android: "assets/launcher/icon.png"
  adaptive_icon_background: "assets/launcher/background.png"
  adaptive_icon_foreground: "assets/launcher/foreground.png"

5. Run the following commands
flutter packages get
flutter packages pub run flutter_launcher_icons:main


6. Verify that you can see the new icon when running flutter run or flutter build and Party 🎉
