# TWRP for Nook Glowlight 4
### State
TWRP builds and is fully functional (hopefully).

### Test without installation
1) enter fastboot;
2) in cmd do `fastboot boot <path_to_recovery_image>`

### Test without installation
Not possible, `fastboot boot <path_to_recovery_image>` is not working on this device :(

### Installation
1) enter fastboot;
2) in cmd do `fastboot flash recovery <path_to_recovery_image>`

### How to build TWRP
1. `repo init --depth=1 -u git://github.com/minimal-manifest-twrp/platform_manifest_twrp_omni.git -b twrp-8.1`
2. `repo sync -n -j 1 && repo sync -l -j 4`
3. `clone this repo to <twrp_repo>/device/nook`
4. apply patches from `<twrp_repo>/device/nook/patches` directory
5. open terminal in `<twrp_repo>` directory;
6. `export LC_ALL=C`
7. `. build/envsetup.sh`
8. `lunch omni_gentoo-userdebug`
9. `mka recoveryimage`

if everything is successful you should find built recovery by path <twrp_repo>/out/target/product/nook_ntx_generic/recovery.img
