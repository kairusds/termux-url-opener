# termux-url-opener
My termux-url-opener script with yt-dlp

## Installation
Install the [Termux:API app](https://f-droid.org/en/packages/com.termux.api/)

Run:

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

## Usage
From the YouTube app or any app, click `Share > More > Termux` and it should give you an option to download the shared link via MP3 or Video from the Termux app.

(For the YouTube app, if the `More` button is not visible, scroll the app icons list horizontally to the right.)

The downloaded MP3 files are stored in the `Music` folder on your internal storage, and the videos are stored on the `Movies` folder.

## Notice
- If you keep getting `Permission denied` errors, just grant the Storage permission again for the Termux app manually on the app info page. Running `termux-setup-storage` again if you already ran the command once wipes your entire internal storage.
