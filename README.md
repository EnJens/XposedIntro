# Xposed
Good links:
Official tutorial: https://github.com/rovo89/XposedBridge/wiki/Development-tutorial
Official installer: https://forum.xda-developers.com/showthread.php?t=3034811
Note that only 7.1.1 and below is supported so far.

## What is Xposed
Xposed is a system patch that allows user applications to hook into
any Android java call in any application.
It requires a patched system, including dalvik, Zygote etc.
Due to the way it's implemented, it allows hooking all types of apps, including system and playstore apps.

Furthermore, it allows replacing resources in apps to change the way they look and are layouted.


## Tl;Dr
1) Create new app (Needs a default activity if you want to use Android Studio to install)
2) Add `provided 'de.robv.android.xposed:api:82'` to app/build.gradle dependencies sections (*must* be provided)
3) Disable Instant Run as it's incompatible (File -> Settings -> Build, Execution, Deployment -> Instant Run)
4) Add new class that implements from de.robv.android.xposed.IXposedHookLoadPackage and overrides handleLoadPackage
5) Add assets folder directly under "app" folder, and put a file called "xposed_init" with the
   full classname of your IXposedHookLoadPackage class (E.g. com.example.ColorEverythingPink)
6) To print logs, import import de.robv.android.xposed.XposedBridge and call `XposedBridge.log("Loaded app: " + loadPackageParam.packageName);` to print out all packages that are loaded.
7) Build & Install
8) In Xposed installer enable the module
9) Reboot device, goto Xposed Installed and look at the logs.

Note that everytime a new version is installed, the phone must be rebooted to apply.

## Getting Starting
See GettingStarted.md for more details
