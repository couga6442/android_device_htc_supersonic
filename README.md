CM10 for the EVO 4G

## Info

|||
|-----------------------------------:|:--------------------------|
|**Discussion thread**: | http://forum.xda-developers.com/showthread.php?t=1625096

## Building 

### Initialize
[setup linux/OS X](http://source.android.com/source/initializing.html) - Please note: it must be sun-java-6, not openjdk

### Prepare to download sources
```bash
mkdir ~/cm10
cd ~/cm10/
curl https://dl-ssl.google.com/dl/googlesource/git-repo/repo > ~/bin/repo
chmod a+x ~/bin/repo
repo init -u git://github.com/CyanogenMod/android.git -b jellybean
```

### Download the source
```bash
cd ~/cm10
repo sync -j16
```
NOTE: This WILL take a long time.

### Finish setting up repo
```bash
wget -O .repo/local_manifest.xml https://raw.github.com/jmztaylor/android_device_htc_supersonic/jellybean/Manifest/local_manifest.xml
```

### Download my sources
```bash
cd ~/cm10
repo sync -j16
```

### Build
Make sure we're in ~/cm9...
```bash
cd ~/cm10
```
Pull in the prebuilts, like Rom Manager...
```bash
./vendor/cm/get-prebuilts
```
And build!
```bash
. build/envsetup.sh && brunch supersonic
```

