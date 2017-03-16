## CoreOS ARM64 Repositories

CoreOS is now releasing official ARM64 builds.  If unsure, you should start with the latest production binary release from here: https://alpha.release.core-os.net/arm64-usr

If you want to make some modifications to CoreOS and build an OS image yourself, then you should probably just build from the upstream CoreOS source repositories.  Follow the CoreOS SDK instructions here https://coreos.com/docs/sdk-distributors/sdk/modifying-coreos.

If you are sure you want to use my development repositories, follow the above CoreOS SDK instructions, but use my manifest when initializing your local repositories:

    repo init -u https://github.com/glevand/coreos--manifest.git
    repo sync
    ./chromite/bin/cros_sdk --create --nousepkg

To build for ARM64 pass ```--board=arm64-usr``` to the CoreOS SDK utilities:

    ~/trunk/src/scripts/build_packages --board=arm64-usr --nousepkg
    ~/trunk/src/scripts/build_image --board=arm64-usr prod dev
