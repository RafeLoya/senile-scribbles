# `encode_av1`

This script attempts to do the following:
- Read a directory for video files
- Determine if encoding said files with AV1 and a given CRF could reduce the file size while maintaining a certain VMAF score
- Encode these files

With default values, it attempts to encode at a CRF with a VMAF score of 95 (in most cases, visually lossless to humans), and does not encode if it can't be achieved without reducing the file size. There are settings to encode at a given CRF anyway if the script decides not to re-encode.

# Dependencies

The following are necessary to use this script:
- [FFmpeg](https://ffmpeg.org/download.html)
- [ab-av1](https://github.com/alexheretic/ab-av1) - Used to determine optimal CRF values
- [Av1an](https://github.com/rust-av/Av1an) - A video encoding framework that chunks encoding processes in parallel

FFmpeg can be installed from the organization's site, and the other two requirements can be installed with `cargo`:
```shell
cargo install ab-av1
cargo install av1an
```
