
LineageOS device configuration for the Lenovo a6020 vibe K5.

How to Build
---------------

Initialise from LineageOS:

     repo init -u https://github.com/LineageOS/android.git -b cm-14.1

Use the following local manifest:

<?xml version="1.0" encoding="UTF-8"?>
<manifest>
  <project name="Pirinvk/android_device_lenovo_A6020" path="device/lenovo/A6020" remote="github" />
  <project name="Pirinvk/android_kernel_lenovo_msm8916" path="kernel/lenovo/msm8916" remote="github" />
  <project name="LineageOS/android_external_bson" path="external/bson" remote="github" />
  <project name="LineageOS/android_external_stlport" path="external/stlport" remote="github" />
  <project name="LineageOS/android_external_sony_boringssl-compat" path="external/sony/boringssl-compat" remote="github" />
  <project name="LineageOS/android_device_qcom_common" path="device/qcom/common" remote="github" />
  <project name="LineageOS/android_packages_resources_devicesettings" path="packages/resources/devicesettings" remote="github" />
  <project name="Pirinvk/android_vendor_lenovo_A6020" path="vendor/lenovo/A6020" remote="github" />
</manifest>


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

<?xml version="1.0" encoding="UTF-8"?>
<manifest>
    <project name="pirinvk/android_kernel_maxwellplus" path="kernel/bq/maxwellplus" remote="github" revision="cm-11.0" />
    <remove-project name="CyanogenMod/android_frameworks_av" />
    <project name="pirinvk/framework_av" path="frameworks/av" revision="master" />
    <project name="pirinvk/android_device_maxwellplus" path="device/bq" revision="master" />
    <project name="pirinvk/android_vendor_maxwellplus" path="vendor/bq" revision="cm-11.0" />
</manifest>

java-6

Sync and build:

    repo sync
    vendor/cm/get-prebuilts
    . build/envsetup.sh
    brunch maxwellplus

