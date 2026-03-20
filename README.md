# Glitch's Ultimate File Hub

## Overview

Glitch's Ultimate File Hub is a Windows desktop toolkit for downloading media from links, converting files, compressing files, and using a fast right-click converter from File Explorer. It is designed to keep common media tasks in one place with a custom theme system, progress tracking, and simple install options.

## Main Features

### 1. Link Converter

The Link Converter lets you paste a supported media link and download it in one of three output modes:

* **MP4**
* **MP3**
* **MP4 (No Audio)**

It also includes:

* **Load Qualities** for MP4 and MP4 (No Audio)
* **Browser cookie support**
* **cookies.txt support**
* **Playlist mode**
* **Open Downloads Folder**
* **Progress bar and live status updates**

### 2. Universal Compressor

The Universal Compressor lets you:

* choose a file manually
* drag and drop a file
* compress video to a target size
* compress audio to a target size
* zip other file types

It also shows:

* current file size
* estimated lowest target size
* progress and status updates

### 3. File Extension Converter

This system has two parts:

#### Full Converter

A full windowed converter for manually choosing files, selecting an output folder, and converting with progress tracking.

#### Quick Right-Click Converter

A smaller quick converter that opens from the Windows right-click menu and converts directly beside the original file.

### 4. Theme and Appearance

The program includes a theme system with:

* dark background by default
* neon accent styling
* customizable colors
* auto-save theme behavior
* restore default colors option

### 5. Folder Settings

You can control where the app stores:

* downloads
* compressed files
* tool data

---

## Installation

### Public installer build

If you installed the program using the Setup executable:

1. Run the installer.
2. Choose an install folder.
3. Finish setup.
4. Launch the app from the Start Menu, desktop shortcut, or installed folder.

### Source/Python build

If you are running the source version directly, you generally need:

* Python
* FFmpeg
* ffprobe
* optionally `tkinterdnd2` for drag and drop

---

## Requirements

### Required for full functionality

* **Windows**
* **FFmpeg** in PATH
* **ffprobe** in PATH

### Optional

* **tkinterdnd2** for drag and drop support in the full converter and compressor

If FFmpeg or ffprobe is missing, download, conversion, and compression tasks that rely on those tools will fail.

---

## Main Menu

When you open the program, you will see these sections:

* **Link Converter**
* **Universal Compressor**
* **Glitch's File Extension Converter**
* **Folder Settings**
* **Appearance**

Each section is explained below.

---

# Link Converter Guide

## What it does

The Link Converter downloads media from a pasted link and outputs it as:

* MP4
* MP3
* MP4 with no audio

## Basic use

1. Open **Link Converter**.
2. Paste a supported media link into the link box.
3. Choose any cookie options if needed.
4. If you want a specific resolution, click **Load Qualities**.
5. Choose one of the output buttons:

   * **MP4**
   * **MP3**
   * **MP4 (No Audio)**
6. Wait for the progress bar and status text to finish.
7. Open the output folder if needed.

## Output modes

### MP4

Use this when you want a standard video file with audio.

How it works:

* the app downloads the best matching video and audio streams
* it attempts a fast MP4 conversion first
* if needed, it falls back to a full compatible conversion
* the final file is saved to your video output folder

### MP3

Use this when you want audio only.

How it works:

* the app downloads the best audio stream available
* FFmpeg converts the audio to MP3
* the file is saved to your video output folder

### MP4 (No Audio)

Use this when you want a silent video file.

How it works:

* the app downloads video only
* audio is removed from the final output
* the final video is saved as MP4

## Load Qualities

**Load Qualities** checks the available resolutions for the current link.

Important notes:

* this mainly applies to **MP4** and **MP4 (No Audio)**
* **MP3** ignores video quality selection
* if playlist mode is on, quality loading uses the **first valid video in the playlist** as the sample
* if quality data cannot be read, the app will stay on **Best Available**

## Playlist mode

If **Download Entire Playlist** is enabled:

* the app treats the link as a playlist when possible
* downloads are stored in a playlist-named folder
* files are usually numbered by playlist order
* quality loading checks the first usable playlist item

Use playlist mode when:

* you want a whole playlist downloaded in one run
* you want output organized by playlist name

Leave it off when:

* you only want one item from a link
* you want the app to behave like a single-video downloader

---

# Cookie Guide

Cookies are one of the most important parts of the Link Converter when a website blocks anonymous access.

## Why cookies matter

Some videos may fail without cookies because they are:

* age-restricted
* login-gated
* region-limited
* part of an account session
* protected in a way that requires a signed-in browser session

Cookies allow the downloader to use your existing session instead of behaving like a completely unsigned-out request.

## Cookie methods in this program

The app supports two cookie methods:

### 1. Use Browser Cookies

This tells the downloader to read cookies from a supported browser profile.

Supported browser choices in the app:

* Edge
* Chrome
* Firefox
* Brave

How to use it:

1. Turn on **Use Browser Cookies**.
2. Choose the correct browser from the dropdown.
3. Start your download.

When to use it:

* you are currently signed in to the website in that browser
* you want the fastest setup
* you do not want to export a cookie file manually

Things to check if it fails:

* make sure the correct browser is selected
* make sure you are actually signed in on that browser
* close and reopen the app after signing in if needed
* some browser profiles or locked sessions may still block access

### 2. Use Saved cookies.txt

This uses a manually exported cookie file.

How to use it:

1. Click **Get Cookie Export Extension** if you need help finding a browser extension.
2. Export your site cookies to a `cookies.txt` file.
3. Click **Select cookies.txt**.
4. The app copies that file into its tool storage area.
5. Turn on **Use Saved cookies.txt**.
6. Start your download.

When to use it:

* browser cookie reading does not work for your setup
* you want a saved reusable cookie file
* you want more control over which session is used

## Cookie priority in this app

If both options are enabled, the program uses them in this order:

1. **Saved cookies.txt**
2. **Browser cookies**

That means if a valid saved cookie file exists and is enabled, it takes priority over browser cookies.

## Saved cookie file behavior

When you select a `cookies.txt` file:

* the app copies it into its own cookie storage folder
* the saved path is remembered in settings
* the status area updates to confirm it was saved

You can also:

* view the saved cookie path inside the Link Converter area
* clear the saved cookie file with **Clear Saved Cookie File**

## When to use cookies

Use cookies if:

* a download says login is required
* a video is age-restricted
* a site blocks standard access
* a member-only or account-based page works in your browser but not in the app

## When not to use cookies

You usually do not need cookies for:

* public videos with no sign-in requirement
* normal open media pages
* sites that do not require session access

## Cookie troubleshooting

If downloads fail even with cookies:

* confirm you are signed in on the selected browser
* try `cookies.txt` instead of browser cookies
* re-export a fresh `cookies.txt`
* make sure the cookie file is not outdated
* make sure the file really belongs to the site you are trying to access
* test with playlist mode off if you only need one item

## Cookie privacy note

A cookie file can represent an active session. Treat it like sensitive account data. Do not share your `cookies.txt` publicly.

---

# Universal Compressor Guide

## What it does

The Universal Compressor helps reduce file size.

It handles three general cases:

* **video compression**
* **audio compression**
* **ZIP compression for other files**

## Choosing a file

You can either:

* click **Choose File**
* drag and drop a file onto the drop area

## File size display

After selecting a file, the app shows:

* current file size
* estimated lowest target size

That estimate is there to help you avoid choosing an unrealistic target.

## Target Size (MB)

For video and audio files, enter the desired output size in megabytes.

The app then calculates a bitrate target based on the file length.

### Video compression

How it works:

* reads video duration with `ffprobe`
* calculates a video bitrate based on your target size
* uses AAC audio and H.264 video for compatibility
* saves a `_compressed.mp4` file in the compressed output folder

Use this when you need:

* smaller upload size
* easier sharing
* lower storage usage

### Audio compression

How it works:

* reads audio duration with `ffprobe`
* calculates an audio bitrate from your target size
* saves a `_compressed.mp3` file

Use this when you need:

* smaller music or voice files
* easier sending or uploading

### ZIP compression

If the file is not recognized as supported video or audio, the app creates:

* a `_compressed.zip`

Use this for:

* documents
* project files
* images or mixed files when normal media compression does not apply

## Compressor tips

* do not set a target size below the estimated minimum if you want usable quality
* if a target is too small, the app may reject it
* ZIP compression depends on the real compressibility of the original file

---

# Full File Extension Converter Guide

## What it does

The full converter is the standalone converter window.

It lets you:

* choose a file manually
* drag and drop a file
* auto-detect file type
* select valid target formats only
* choose an output folder
* convert with progress tracking

## Supported file families

### Video

Typical supported inputs include:

* MP4
* MKV
* MOV
* AVI
* WEBM
* M4V
* WMV
* MPEG
* MPG
* TS

Possible outputs include:

* MP4
* MKV
* MOV
* AVI
* WEBM
* MP3

### Audio

Typical supported inputs include:

* MP3
* WAV
* FLAC
* AAC
* OGG
* OPUS
* M4A
* WMA

Possible outputs include:

* MP3
* WAV
* FLAC
* AAC
* OGG
* OPUS
* M4A

### Image

Typical supported inputs include:

* PNG
* JPG
* JPEG
* WEBP
* BMP
* GIF

Possible outputs include:

* PNG
* JPG
* JPEG
* WEBP
* BMP
* GIF

## How to use the full converter

1. Open **Glitch's File Extension Converter**.
2. Click **Choose File** or drag a file into the window.
3. Let the app detect the file type.
4. Pick the desired target format from the dropdown.
5. Click **Choose Output Folder**.
6. Click **Convert File**.
7. Wait for the progress bar to complete.

## Notes

* the dropdown only shows valid formats for the selected file family
* the converter avoids offering the same extension as the current one
* the selected output folder controls where the result is saved

---

# Quick Right-Click Converter Guide

## What it does

The quick right-click converter is a smaller conversion window launched from File Explorer.

It is designed for speed.

Instead of opening the full converter, it:

* reads the file you clicked
* detects the family automatically
* shows only valid target formats
* saves beside the original file

## How to use it

1. In File Explorer, right-click a supported file.
2. Click **Glitch's File Extension Converter**.
3. The quick converter window opens.
4. Choose the output format.
5. Click **Convert**.

## Multi-file behavior

The quick converter supports multiple selected files when the selection is compatible.

Important rules:

* all selected files must be from the same family

  * all video, or all audio, or all image
* mixed families are not allowed in the same batch
* unsupported files are ignored
* output files are saved beside each original file

## Naming behavior

If an output filename already exists, the converter creates a unique new name instead of overwriting automatically.

---

# Converter Install/Management Section

## What this section does

Inside the main hub, the converter management area can:

* install/register the converter system
* launch the full converter
* open the install folder
* uninstall/remove the converter system

Depending on whether you are using the source version or the packaged installer version, this area may either copy supporting files or register the EXE-based converter tools already included in the installation.

## Buttons

### Install Converter

Used to set up the converter tools and right-click integration.

### Launch Converter

Opens the full converter directly.

### Open Install Folder

Opens the folder where the converter files or packaged converter build are stored.

### Uninstall Converter

Removes the converter integration, usually including right-click registration and shortcut setup.

---

# Folder Settings Guide

## What it controls

Folder Settings lets you choose where the app stores its main outputs and tool data.

Typical categories include:

* tool install folder
* video output folder
* compressed output folder

## How to use it

1. Open **Folder Settings**.
2. Use **Browse** to select folders.
3. Save your changes.

## Why this matters

Changing these folders helps you:

* keep downloads organized
* separate compressed files from raw files
* move tool data away from crowded locations

---

# Appearance and Theme Guide

## What you can customize

The appearance system supports custom colors for the UI theme.

Typical theme areas include:

* background color
* text color
* accent color

## Theme behavior

* theme changes auto-save
* saved theme loads again when the app is reopened
* you can restore default colors

## Tips

* use high contrast colors for readability
* bright accents work best on dark backgrounds
* if a window looks outdated, reinstall or refresh the converter setup so installed copies match the current theme system

---

# Progress and Status Messages

Most major actions in the program show:

* a progress bar
* a status line

You will see this during:

* downloads
* conversions
* compression
* playlist processing
* converter setup actions

This helps you track whether the app is:

* loading information
* downloading
* converting
* processing output
* finished
* failed

---

# Common Problems and Fixes

## FFmpeg missing

Problem:

* conversion or download tasks fail immediately

Fix:

* install FFmpeg and ffprobe
* make sure both are available in PATH

## Cookie-related download failure

Problem:

* login or age-restricted content does not download

Fix:

* turn on browser cookies and select the correct browser
* or export a fresh `cookies.txt` and use that instead

## No quality list appears

Problem:

* clicking **Load Qualities** does not populate extra options

Fix:

* confirm the link is valid
* confirm the site is reachable
* try cookies if the page needs login
* try with playlist mode off if you are testing a single link

## Right-click converter looks outdated

Problem:

* the quick converter does not match the current theme or behavior

Fix:

* reinstall or re-register the converter system so the installed version matches the current build
* close any older quick-converter process before testing again

## Permission errors in Program Files

Problem:

* settings or data fail to save in an installed build

Fix:

* use the current build where settings are stored in user-writable locations such as AppData, Documents, or Downloads

---

# Best Practices

* keep FFmpeg and ffprobe available
* use cookies only when needed
* protect your `cookies.txt`
* use playlist mode only when downloading full playlists
* choose realistic compression targets
* keep your output folders organized with Folder Settings
* reinstall converter integration after major app updates if required

---

# Summary

Glitch's Ultimate File Hub combines downloading, conversion, compression, quick right-click actions, and theme customization into one Windows app.

It is best used when you want:

* quick media downloads from links
* simple video, audio, or image conversion
* file compression without jumping between different tools
* a fast File Explorer right-click converter
* a customizable look with saved theme settings
