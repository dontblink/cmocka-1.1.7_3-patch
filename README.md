# cmocka-1.1.7_3-patch
meson patch file for cmocka 1.1.7  
as of meson 1.3.0, `install: true` will override `build_by_default:false`, which leads to meson building libraries even if there are no dependencies on said library. For my use case, this is problematic when I cross compile - the non-native library can't be built with my cross-compile toolchain, but meson will attempt (and fail) to build it.  
This patch sets `install: false` to all library targets, and is based of [cmocka-1.1.7_2-patch](https://wrapdb.mesonbuild.com/v2/cmocka_1.1.7-2/cmocka.wrap) from wrapdb  
Relevant git issue: https://github.com/mesonbuild/meson/issues/12530


corresponding cmocka.wrap:
```ini
[wrap-file]
directory = cmocka-1.1.7
source_url = https://cmocka.org/files/1.1/cmocka-1.1.7.tar.xz
source_filename = cmocka-1.1.7.tar.xz
source_hash = 810570eb0b8d64804331f82b29ff47c790ce9cd6b163e98d47a4807047ecad82
patch_filename = cmocka_1.1.7-3_patch.zip
patch_url = https://github.com/dontblink/cmocka-1.1.7_3-patch/releases/download/v1.0/cmocka_1.1.7-3_patch.zip
patch_hash = f89bb5feadaa9611bb124a8c31ed479416818e4389251758a966b8a44f184e32
```

For those following along using this as an example of how to make patch files:  
Zip file name needs to match `patch_filename`  
Folder at root of zip needs to match `directory`  
Make a release out of said zip file, or upload to your preferred file server to get a url for `patch_url`  
To get `patch_hash`, take the zip to https://md5file.com/calculator and grab the SHA256 hash (no way to grab this straight from github at the moment)
