
------------------------------------------------------------------------------------------------------------------------------
------------------------------------------------------------------------------------------------------------------------------

LineageOS device configuration for the Lenovo a6020 vibe K5.

How to Build
---------------

Initialise from LineageOS:
repo init -u https://github.com/LineageOS/android.git -b cm-14.1
Use the following local manifest:

    <?xml version="1.0" encoding="UTF-8"?>
    <manifest>

XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
    </manifest>

java-9

Sync and build:

repo sync -c --force-broken --force-sync
source build/envsetup.sh
croot
export ANDROID_JACK_VM_ARGS="-Dfile.encoding=UTF-8 -XX:+TieredCompilation -Xmx4G"
export JAVA_OPTIONS="-Xmx4G"
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

    <?xml version="1.0" encoding="UTF-8"?>
    <manifest>

XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
    </manifest>

java-6

Sync and build:

    repo sync
    vendor/cm/get-prebuilts
    . build/envsetup.sh
    brunch maxwellplus

