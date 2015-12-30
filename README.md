# cocos2d-x-cpp-android-studio-template
The goal of this repo is to enhance Cocos2d-x C++ Android Studio project template. The enhancement is meant to leverage the latest stable Android SDK build tool, targeting the uppermost API level.

Latest Cocos2d-x version is 3.9. At the time it came out, the Android SDK build tool used by its templates (that is to say, any new Cocos2d-x project that you create with the command `cocos new <project>`) is 22.0.1 and both the `compileSdkVersion` and `targetSdkVersion` are API level 22 (Lollipop).

This repo offers alternative C++ Android Studio project template files that already apply Android SDK build tool 23.0.2, compiling and targeting API level 23 (Marshmallow).

Frequently Asked Questions (FAQ)
============================
### What's the point in targeting the latest Android API level?
While `targetSdkVersion` doesn't mean that your app users need an Android device in that API level exclusively (that's what `minSdkVersion` is for), there are derived benefits in taking the move. For example, API 23 comes with a [revised, more flexible permission model](http://developer.android.com/about/versions/marshmallow/android-6.0-changes.html#behavior-runtime-permissions) or a [brand new auto backup for apps feature](http://developer.android.com/about/versions/marshmallow/android-6.0.html#backup).
These enhancements are locked when you don't target the latest Sdk version, even if users run your app in devices on that API level or later.

### How to apply it?
> - Clone this project in a temporary directory, that you will be ready to delete once you have applied this bundle.
> - In a terminal window, run the following two commands:
> ```
> $ cp -R <temporary dir>/cocos <your/cocos2d-x/root>/
> $ cp -R <temporary dir>/templates <your/cocos2d-x/root>/
> ```
> - For example, if you cloned this repo in `$HOME/cocos2d-x-cpp-android-studio-template` and you have Cocos2d-x installed in `$HOME/bin/cocos2d-x`, you would have to enter
> ```
> $ cp -R ~/cocos2d-x-cpp-android-studio-template/cocos ~/bin/cocos2d-x/
> $ cp -R ~/cocos2d-x-cpp-android-studio-template/templates ~/bin/cocos2d-x/
> ```

### Why not to just tweak my resulting project files?
You probably already work in a Cocos2d-x project and don't start a new one every other day. That being said, you can just check this repo commits to see exactly what needs to be done to make your existing project apply the latest and greatest of the Android SDK.
There are a couple of caveats, though:
> 1. You must repeat the steps in every associated project. Most notably, in the libcocos2dx dependency. By copying this bundle into the official C++ Android Studio project template, you get the whole, end-to-end upgrade done in one coup.
> 2. Android API level 23 (Marshmallow) has some breaking changes that make libcocos2dx build to fail. In particular [the removal of Apache HTTP Client](http://developer.android.com/about/versions/marshmallow/android-6.0-changes.html#behavior-apache-http-client) makes the compilation of `Cocos2dxDownloader.java` to fail. Therefore, the entire application build, as it depends of libcocos2dx. This bundle contains a workaround and the show goes on.

### Is this project a fork of the main Cocos2d-x one?
Not at all. It only contains the C++ Android Studio project template delta that upgrades such template so it leverages the latest and greatest of the Android platform and tools.
The reason it's in its own git repo is to keep source version control. Keep reading.

### What happens when Cocos2d-x releases new versions in the stable channel?
If it targets the latest and greatest version of the Android platform and tools, we'll post a note here highlighting that we don't have any value to add in this regard.
If it doesn't, expect that we'll update this repo so the patch is applicable to the latest and greatest Cocos2d-x framework.

### What happens when AOSP (the official Android Open Source Project) releases new versions in the stable channel?
Likewise, the goal of this repo is to complement the latest and greatest Cocos2d-x project so that it leverages the latest and greatest version of the Android platform and tools.

### Wouldn't be better to contribute this patch to Cocos2d-x?
It's the idea. After all, we all owe so much to Cocos2d-x guys that contributing back with our own effort is the least that we can do (not to say "must"). They still have veto power and possibly valid reasons to reject the patch, or to delay its acceptance, promotion to master.
In the meantime... hey, we got a solution. Why to keep it under wraps?

### Can I contribute to this repo?
There's nothing that we could appreciate more. We may not have time to react fast enough when a new release (either of Cocos2d-x or AOSP) hits the streets. If you have the chance to get there faster than us and want to share your achievement with the broader community, we all be pleased. Keep in mind that you can also contribute with the same patch to the official Cocos2d-x project.
