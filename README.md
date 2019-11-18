# linux-tools
Miscellaneous Linux Scripts

## change-hostname

Change your Linux hostname easily. Only for Debian-based distros.

## install-lamp

Install a LAMP stack on Debian Buster.

## fio-test

Test the filesystem performance of a specified drive/array. Destructive. Uses fio.

Tests include: Random Read, Random Write, Sequential Read, Sequential Write

## ytdl

youtube-dl is a very good tool for downloading content from YouTube on Linux, but its command line is rather onerous. ytdl simply provides a front-end to perform some of the most often needed tasks, like downloading the best quality video as MP4, or extracting audio to MP3. It also includes the ability to install or update the installed version of youtube-dl.

Install ytdl:
```
sudo wget https://raw.githubusercontent.com/Cat5TV/linux-tools/master/ytdl -O /usr/local/bin/ytdl
sudo chmod a+rx /usr/local/bin/ytdl
```

## wallpaper

Rotate desktop wallpaper on a timer. Works on Linux Mint 19, and probably others.

Open the shell script and modify the srcfolder, destfile and seconds variables.

Run via cron like this:

```
@reboot /path/to/wallpaper
```

It will continually crawl through the srcfolder for any file with the .jpg extension and overwrite destfile each time.
