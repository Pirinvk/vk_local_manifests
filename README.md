
LineageOS device configuration for the Lenovo a6020 vibe K5.

How to Build
---------------

Initialise from LineageOS:

     repo init -u https://github.com/LineageOS/android.git -b cm-14.1

Use the following local manifest:

java-9

Sync and build:

repo sync -c --force-broken --force-sync

in /Build/Core/config.mk edit the line:
 # APICHECK_COMMAND := $(APICHECK) -JXmxXXXXm -J"classpath $(APICHECK_CLASSPATH)"

to:

 # APICHECK_COMMAND := $(APICHECK) -JXmx3036m -J"classpath $(APICHECK_CLASSPATH)"

source build/envsetup.sh

croot

export ANDROID_JACK_VM_ARGS="-Dfile.encoding=UTF-8 -XX:+TieredCompilation -Xmx3G"

export JAVA_OPTIONS="-Xmx3G"

export USE_NINJA=false

brunch A6020



------------------------------------------------------------------------------------------------
------------------------------------------------------------------------------------------------
------------------------------------------------------------------------------------------------


CyanogenMod device configuration for the bq Maxwell Plus.

How to Build
---------------

Initialise from CyanogenMod:

    repo init -u git://github.com/CyanogenMod/android.git -b cm-11.0

Use the following local manifest:

java-6

Sync and build:

    repo sync
    vendor/cm/get-prebuilts
    . build/envsetup.sh
    brunch maxwellplus

