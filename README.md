# flutter_bugfender

A Bugfender Wrapper plugin (implementing native code) for Flutter Projects.

**Note:** This plugin was provided by the community, hence it is published "AS IS", our support might not always be able to help you.

## Using the package

Edit `pubspec.yaml` and add add `flutter_bugfender` to `dev_dependencies`:

```
dev_dependencies:
  flutter_test:
    sdk: flutter
  flutter_bugfender: ^2.0.1
```

Then run `flutter pub get` (or ‘Packages Get’ in IntelliJ) to download the package.

Edit `lib/main.dart` and add an import:

```
import 'package:flutter_bugfender/flutter_bugfender.dart';
```

And in your main application builder:

```
FlutterBugfender.init("YOUR_APP_KEY", enableAndroidLogcatLogging: false);
```

There are other init options:
 * apiUri and baseUri: alternative URLs for on-premise installations
 * maximumLocalStorageSize: maximum size the local log cache will use, in bytes
 * printToConsole: whether to print to console or not
 * enableUIEventLogging: enable automatic logging of user interactions
 * enableCrashReporting: enable automatic crash reporting
 * enableAndroidLogcatLogging: enable automatic logging of logcat (Android only)
 * overrideDeviceName: specify a name for the device

You can also call:

 * FlutterBugfender.log("Working fine!");
 * FlutterBugfender.fatal("Fatal sent!");
 * FlutterBugfender.error("Error sent!");
 * FlutterBugfender.warn("Warning sent!");
 * FlutterBugfender.info("Info sent!");
 * FlutterBugfender.debug("Debug sent!");
 * FlutterBugfender.trace("Trace sent!");
 * FlutterBugfender.setDeviceString("user.email", "example@example.com");
 * FlutterBugfender.setDeviceInt("user.id", 32);
 * FlutterBugfender.setDeviceFloat("user.pi", 3.14);
 * FlutterBugfender.setDeviceBool("user.enabled", true);
 * FlutterBugfender.removeDeviceKey("user.pi");
 * FlutterBugfender.sendCrash("Test Crash", "Stacktrace here!");
 * FlutterBugfender.sendIssue("Test Issue", "Issue value goes here!");
 * FlutterBugfender.sendIssueMarkdown("Test Issue with markdown", "Issue _value_ **goes** here!");
 * FlutterBugfender.sendUserFeedback("Test user feedback", "User feedback details here!");
 * FlutterBugfender.setForceEnabled(true);
 * FlutterBugfender.forceSendOnce();
 * FlutterBugfender.getDeviceUri());
 * FlutterBugfender.getSessionUri());

