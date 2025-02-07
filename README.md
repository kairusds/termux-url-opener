# termux-url-opener
My termux-url-opener script with yt-dlp

## Installation
Install the [Termux:API app](https://f-droid.org/en/packages/com.termux.api/)

Run these commands:

```sh
termux-setup-storage
pkg update
pkg upgrade
pkg install python3 aria2 ffmpeg jq termux-api wget
pip install --upgrade yt-dlp
mkdir ~/bin
wget https://github.com/kairusds/termux-url-opener/raw/master/termux-url-opener -P ~/bin
chmod +x ~/bin/termux-url-opener
```

And you should be good to go.

## Usage
From the YouTube app or any app, click `Share > More > Termux` and it should give you an option to download the shared link via MP3 or Video from the Termux app.

(For the YouTube app, if the `More` button is not visible, scroll the app icons list horizontally to the right.)

The downloaded MP3 files are located on the `Music` folder on your Android internal storage, the same goes for videos too but it's on the `Movies` folder instead.

## Notice
- As of today on Feb 29, 2024, ffmpeg v6 seems to be incompatible with the `trim video` feature. This only happens specifically with Termux/Android and not any other Linux distro.
- If you keep getting `Permission denied` errors, just regrant the Storage permission for the Termux app manually on its app info page. Running `termux-setup-storage` again if you already ran the command once wipes your entire internal storage.
