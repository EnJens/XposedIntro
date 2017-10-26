# Installation

For the purpose of this test,
it is assumed that Xposed is already installed and working.

But, for clarity, the steps required are:

1) Ensure you have a boot image flashed with dm-verity disabled! Otherwise, Xposed installation will cause the device to not boot! Generally any rooted image will have this done.
2) Install TWRP
3) Flash the xposed zip matching your OS version (7.1.1 64-bit http://dl-xda.xposed.info/framework/sdk25/arm64/xposed-v88.1-sdk25-arm64.zip)
4) Install XposedInstaller (*required*) and verify it works

That's it.
Root is not strictly required as this patches the system when installed.
