# **Instabug for Mobile Games**  
Detailed bug reporting and in-app chat for mobile games made on Android, iOS, and Unity!


<img src="https://user-images.githubusercontent.com/9888943/41102891-337c4170-6a68-11e8-8b89-73f60ab6ad81.png" width="35%"/><img src="https://user-images.githubusercontent.com/9888943/41102892-339dab08-6a68-11e8-895c-89c5c92dc4ed.png" width="63%"/> 


Collect in-game bug reports and feedback and speed up your game development cycle with Instabug. Forward your bugs automatically to Trello, Jira, Slack, Github, Gitlab & more.

For more info, visit Instabug for Unity on [Instabug.com](https://www.instabug.com/platforms/unity).

## Installation (iOS)

1.  Add Instabug for iOS on the [Asset Unity Store here](https://assetstore.unity.com/packages/tools/integration/instabug-for-ios-116191).
   
2.  Add an empty GameObject to your project, and add the InstabugiOS script component to it.
   
3.  Click on Add Component, search for InstabugiOS, and add it to the game object.
   
4.  Add your app token, and change the invocation event from Unity’s Inspector directly.

## Installation (Android)

1.  Add Instabug for Android on the [Asset Unity Store here](https://assetstore.unity.com/packages/tools/integration/instabug-for-android-116200).

2.  Export your Unity project by opening Build Settings from “File —> Build Settings”, and checking the Export button. Choose your desired path to save the project.
   
3.  Open the exported project from Android Studio, and add the following changes to the build.gradle file.
```
        ...
        allprojects {
           repositories {
              jcenter()
              google()
              maven {
      // TODO add this only if interested in getting SNAPSHOT releases
      url 'https://oss.sonatype.org/content/repositories/snapshots' }
      ... }
        }
        ...
        dependencies {
      ...
      compile 'com.instabug.library:instabug:5.0.0.3.19-SNAPSHOT'
      }
      ...
```
4. Create a new Application.java class that should look like this. Add your app token, and change the invocation event from this class.
```
  ...
        import android.app.Application;
        import com.instabug.library.Instabug;
        import com.instabug.library.invocation.InstabugInvocationEvent;
        ...
        public class MyApp extends Application {
        @Override
        public void onCreate() { super.onCreate();
        // You can change the invocation event to NONE, FLOATING_BUTTON, // SCREENSHOT_GESTURE, or TWO_FINGER_SWIPE_LEFT.
        new Instabug.Builder(this, "YOUR_APP_TOKEN")
        .setInvocationEvent(InstabugInvocationEvent.SHAKE)
        .build(); Instabug.setUnityEnabled(true);
        } }
```
5. Add the Application class name to the AndroidManifest.xml file.
```
      <manifest xmlns:android="http://schemas.android.com/apk/res/android" ...> ...
       <application android:name=".MyApp" ...> ...
       </application>
       ...
       </manifest>
```


 
  ## Steps
 
**1. Add Instabug to Your Game**
See Installation steps above.

**2. Shake The Phone** 
Your users can shake their devices to report bugs or submit their feedback from within your app with zero interruption to their experience.

**3. View Detailed Bug Reports**
With each bug report your users submit, we automatically capture comprehensive metadata to help you identify the cause of errors and fix issues faster.


## Documentation

For more details about the supported APIs and how to use them, you can check our  [**Documentation**](https://docs.instabug.com/docs/unity).

## Contact Us

If you have any questions or feedback don’t hesitate to get in touch. You can reach us at any time through  **[support@instabug.com](mailto:support@instabug.com)**.
