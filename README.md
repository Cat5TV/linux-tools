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

youtube-dl is a very good tool for downloading content from YouTube on Linux, but its command line is rather onerous. ytdl simply provides a front-end to perform some of the most often needed tasks, like downloading the best quality video as MP4, extracting audio to MP3, or downloading the captions to a file. It also includes the ability to install or update the installed version of youtube-dl.

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

## wifi-check

This script will read wifi-check.cfg in the same directory, or a cfg file designated by --cfg=

The cfg file should be a different hostname, IP address or domain name per line, plain text. Once a config is found, each host is checked via a simple ping. Modify the result of the host being up or down near the end of the script.

I called it wifi-check due to its original purpose: I have a static IP address (DHCP Reservation) assigned to each of my staff's smartphones when connected to my wifi. Then, I run this script every 1 minute via cron. If a staff member is connected to WiFi, it is logged that they are on location. Once they are disconnected from our WiFi (presumably out of distance), it is logged that they are gone.

Example cfg file: [wifi-check.cfg](wifi-check.cfg)

## resize-to-size

I feel like all the resize tools out there are based on dimensions. 1920x1080. 640x480. But I often encounter situations (like YouTube thumbnails) where the limitations for the upload are based upon filesize, not dimensions. So, I created resize-to-size: a bash script that allows you to resize an image based on the filesize (in MB).

The script goes through three phases, designed to achieve the best possible visual quality while meeting your filesize requirement.

Stage 1: Attempt to increase the JPG compression, but never dip below 70%.

Stage 2: Gradually reduce the image scale while also adjusting compression to try to achieve the largest image with no less than 70% quality.

Stage 3: Get aggressive and allow much higher compression.

Usage: `./resize-to-size SIZE_IN_MB FILENAME`

Example: `./resize-to-size 2 sample.jpg` Will scale and compress sample.jpg to 2 MB

## surveillance_converter

A bash script I wrote to take AVI files from our surveillance DVR, fix the pixel aspect ratio (2:1) to create 16:9 H.265 A/V files quickly, ready for viewing or pulling into DaVinci Resolve.
