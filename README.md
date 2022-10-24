# termux-url-opener
My termux-url-opener script with yt-dlp

## Installation
Install the [Termux:API app](https://f-droid.org/en/packages/com.termux.api/)

```sh
pkg update
pkg install python3 ffmpeg jq build-essential termux-api
pip install --upgrade yt-dlp
export PATH=$(which ffmpeg):$PATH

# Run this command to remove build-esssential dependencies and ndk-sysroot to free up storage
# You can also keep it so you don't have to reinstall it everytime yt-dlp gets an update
apt autoremove autoconf automake bc bison build-essential clang cmake flex gperf jsoncpp libarchive libcompiler-rt libllvm libltdl libtool libuv lld llvm m4 ndk-sysroot perl rhash
```

Termux doesn't recognize yt-dlp's binary with termux-url-opener for some
reason so you have to install the PIP version instead.
