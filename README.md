# termux-url-opener
My termux-url-opener script with yt-dlp

## Installation
Install the [Termux:API app](https://f-droid.org/en/packages/com.termux.api/)

```sh
pkg update
pkg install python3 ffmpeg jq termux-api
pip install --upgrade yt-dlp
```

Termux doesn't recognize yt-dlp's binary with termux-url-opener for some
reason so you have to install the Python PIP version instead.

## Notice
- ffmpeg v6.0+ seems to be breaking the `trim video` feature at the moment. Specifically only on Termux and not any other Linux distro.
- If you keep getting `Permission denied` errors, just regrant the Storage permission
for the Termux app manually on its app info page. Running `termux-setup-storage` again wipes your entire internal storage.
