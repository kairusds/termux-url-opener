# termux-url-opener
My termux-url-opener script with yt-dlp

## Installation
Install the [Termux:API app](https://f-droid.org/en/packages/com.termux.api/)

### Paste these commands into Termux and run them one by one

```sh
cd ~
termux-setup-storage
pkg update
pkg upgrade
pkg install python3 aria2 ffmpeg jq termux-api wget nano
mkdir -p yt-dlp
wget https://github.com/yt-dlp/yt-dlp/releases/latest/download/yt-dlp -O yt-dlp/
chmod +x yt-dlp/yt-dlp
echo 'export PATH="$PATH:/yt-dlp"' >> .bashrc
source .bashrc
mkdir ~/bin
wget https://github.com/kairusds/termux-url-opener/raw/master/termux-url-opener -P ~/bin
chmod +x ~/bin/termux-url-opener
```

### Getting cookies.txt file for `yt-dlp`
1. Install and run a Firefox-based browser for Android: [Original Firefox](https://play.google.com/store/apps/details?id=org.mozilla.firefox), [Iceraven](https://github.com/fork-maintainers/iceraven-browser/releases/latest) or [IronFox](https://gitlab.com/ironfox-oss/IronFox/-/releases)
2. Install the [Get cookies.txt LOCALLY](https://addons.mozilla.org/en-US/firefox/addon/get-cookies-txt-locally/) Firefox extension
3. Open a Private Tab by clicking the Tabs icon > then the Mask icon, and login to [YouTube](https://youtube.com). **WARNING: USE A THROWAWAY ACCOUNT FOR THIS SINCE THERE'S A SMALL CHANCE YOUR YOUTUBE/GOOGLE ACCOUNT COULD GET BANNED.**
4. Enable "Get cookies.txt LOCALLY" for Private tabs on the Extensions menu by pressing the 3-dots menu icon > Extensions > Find and tap "Get cookies.txt LOCALLY" > Enable "Run in private browsing". Then, click Permissions > Enable "Allow for all sites" to effectively activate the extension.
5. While on the same YouTube private tab with the logged in account, click "Get cookies.txt LOCALLY" from the same Extensions menu from step 4 then press "Copy".
6. In Termux, run `nano ~/yt-dlp/.youtube.com_cookies.txt` and hold-tap the Termux screen then Press Paste. Afterwards, Press Ctrl+X > Press Y > Press Enter to save the file.
6. In Termux again, paste and run this command: `echo '--cookies ~/yt-dlp/.youtube.com_cookies.txt' > ~/yt-dlp/yt-dlp.conf`
7. Disable "Get cookies.txt LOCALLY" under Extensions Manager from the same Extensions menu in step 4 > Find and click "Get cookies.txt LOCALLY" > Toggle Enabled. (This is not mandatory but still a great security practice in case the extension gets compromised)

`yt-dlp` should be working fine now if you setup the cookies correctly.

## Usage
From the YouTube app or any app, click `Share > More > Termux` and it should give you an option to download the shared link via MP3 or Video from the Termux app.

(For the YouTube app, if the `More` button is not visible, scroll the app icons list horizontally to the right.)

The downloaded MP3 files are stored in the `Music` folder on your internal storage, and the videos are stored on the `Movies` folder.

## Notice
- If you keep getting `Permission denied` errors, just grant the Storage permission again for the Termux app manually on the app info page. Running `termux-setup-storage` again if you already ran the command once wipes your entire internal storage.
