# Multirom Manifest

## Repo sync TWRP Android 8.1
```
mkdir -p ~/multirom && cd ~/multirom
```
```
repo init --depth=1 -u git://github.com/Linux-On-Sdm6Series.git -b mrom-8.1
```
```
repo sync --fetch-submodules
```
## Multirom Repo
```

rm -rf ~/multirom/bootable/recovery
git clone -b android-8.1-mrom https://github.com/vasishath/android_bootable_recovery ~/multirom/bootable/recovery
git clone -b android-9.0 https://github.com/vasishath/multirom system/extras/multirom
cd ~/multirom/system/extras/multirom
git submodule update --init
cd ~/multirom
git clone https://github.com/vasishath/libbootimg ~/multirom/system/extras/libbootimg

```
## Device Source
```

~/multirom/device/$VENDOR/$DEVICE

```
## Build 
```

export ALLOW_MISSING_DEPENDENCIES=true
source build/envsetup.sh
lunch omni_$DEVICE-eng
make recoveryimage

```
