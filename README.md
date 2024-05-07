# cmocka-1.1.7_3-patch
meson patch file for cmocka 1.1.7
as of meson 1.3.0, `install: true` will override `build_by_default:false`, which leads to meson building libraries even if there are no dependencies on said library. For my use case, this is problematic when I cross compile - the non-native library can't be built with my cross-compile toolchain, but meson will attempt (and fail) to build it.
Relevant git issue: https://github.com/mesonbuild/meson/issues/12530


corresponding wrap-file:
```ini
[wrap-file]
directory = cmocka-1.1.7
source_url = https://cmocka.org/files/1.1/cmocka-1.1.7.tar.xz
source_filename = cmocka-1.1.7.tar.xz
source_hash = 810570eb0b8d64804331f82b29ff47c790ce9cd6b163e98d47a4807047ecad82
patch_filename = cmocka_1.1.7-3_patch.zip
patch_url = https://downgit.github.io/#/home?url=https://github.com/dontblink/cmocka-1.1.7_3-patch/blob/main/cmocka-1.1.7-3_patch.zip
patch_hash = 36e518fc25192fc679cbe3279205d9c25a77c09097556cc4eae5e4f16e736377
```
