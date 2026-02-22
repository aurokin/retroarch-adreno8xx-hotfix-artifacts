# RetroArch Adreno 8xx/X1 GL2 Hotfix Artifacts

Short-term user-facing distribution for the Snapdragon Elite / Adreno 8xx GL black-screen fix while upstream review is in progress.

This is not an official RetroArch release.

## Test reference
Primary validation device:
- Odin 3 (Android 15, Qualcomm Snapdragon 8 Elite, Adreno 830)

## What this contains
Use the **Releases** page for downloadable binaries:
- `retroarch-aarch64-adreno8xx-gl2fix.apk`
- `patch-retroarch-gl2-adreno8xx-x1-texstorage-guard.patch`
- `retroarch-stock-coretest2_to_gl2fix.xdelta3`
- `DOWNLOAD_SHA256SUMS.txt`

## Quick install
```bash
adb install -r -d retroarch-aarch64-adreno8xx-gl2fix.apk
```

## Source patch usage
```bash
git apply patch-retroarch-gl2-adreno8xx-x1-texstorage-guard.patch
```

## Optional xdelta usage
This xdelta applies only to one exact base APK build.

```bash
xdelta3 -d \
  -s retroarch-stock-com.retroarch.aarch64.coretest2.apk \
  retroarch-stock-coretest2_to_gl2fix.xdelta3 \
  retroarch-aarch64-adreno8xx-gl2fix.apk
```

## Verification
```bash
sha256sum -c DOWNLOAD_SHA256SUMS.txt
```

## Tracking
- RetroArch issue: https://github.com/libretro/RetroArch/issues/17771
- Mupen thread: https://github.com/libretro/mupen64plus-libretro-nx/issues/575
