# APK archive

This branch stores a split APK as ordinary Git files. **Git LFS is not used.**

- Original filename: `base.apk`
- Original size: 86,183,746 bytes
- Split size: 20 MiB per part (last part may be smaller)
- Number of parts: 5
- Original SHA-256: `85fefed7d42fc960e8306da5ffe79fd2f2c79b53b6f4c6555e0dec6e20021559`

## Reassemble on Windows

Download/clone this branch, open Command Prompt in the repository root, then run:

```bat
copy /b "apk_parts\base.apk.part*" "base.apk"
certutil -hashfile "base.apk" SHA256
```

The SHA-256 output must match the value above.

## Reassemble on macOS / Linux

From the repository root:

```sh
cat apk_parts/base.apk.part0000 apk_parts/base.apk.part0001 apk_parts/base.apk.part0002 apk_parts/base.apk.part0003 apk_parts/base.apk.part0004 > "base.apk"
sha256sum "base.apk"
```

The SHA-256 output must match the value above. Only install or run APKs from sources you trust.
