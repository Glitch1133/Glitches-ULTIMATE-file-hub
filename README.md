# GL!TCH Ultimate File Hub

**GL!TCH Ultimate File Hub** is an all-in-one Windows desktop toolkit for downloading media, converting files, compressing media, managing output locations, and performing quick conversions directly from File Explorer.

The application is designed around a custom dark GL!TCH interface while keeping common media tools in one place.

> **Current Release: v1.2.0**

[Download the Latest Release](../../releases/latest)

---

## Main Features

### Link Converter

Download supported media directly from a link.

Features include:

- Automatic media preview
- Thumbnail preview
- Embedded thumbnails for supported formats
- Video quality selection
- Best Available quality mode
- Playlist support
- Download progress and status
- Automatic yt-dlp update system
- FFmpeg processing
- Deno support for compatible extraction workflows
- Firefox authentication fallback for media that requires a signed-in session
- Automatic retry handling for failed downloads

### Supported Download Formats

Video formats include:

- MP4
- MP4 without audio
- MKV
- MOV
- AVI
- WebM
- M4V
- WMV
- MPEG
- MPG
- TS

Audio formats include:

- MP3
- WAV
- FLAC
- AAC
- OGG
- Opus
- M4A
- WMA

Format availability can depend on the source website and available media streams.

---

## Universal Compressor

Compress video and audio toward a target file size.

Features include:

- Target-size compression
- Adaptive multi-pass compression
- Automatic bitrate adjustment
- Resolution adjustment when necessary
- Audio bitrate optimization
- Repeated compression passes for difficult targets
- Progress information
- Output folder management

Other file types can also be packaged into compressed ZIP files.

---

## File Extension Converter

Convert, repair, and re-encode supported media files.

### Video

Supports formats including:

- MP4
- MKV
- MOV
- AVI
- WebM
- M4V
- WMV
- MPEG
- MPG
- TS
- M2TS
- MTS
- FLV
- 3GP
- OGV
- VOB
- ASF
- MXF

### Audio

Supports formats including:

- MP3
- WAV
- FLAC
- AAC
- OGG
- Opus
- M4A
- WMA
- AC3
- AIFF
- MP2
- MKA
- CAF
- AU

### Images

Supports formats including:

- PNG
- JPG / JPEG
- WebP
- BMP
- GIF
- TIFF
- ICO
- TGA
- PPM
- PGM
- PBM
- DDS
- QOI
- JP2

Actual codec support can vary depending on the included FFmpeg build.

---

## File Explorer Quick Converter

GL!TCH Ultimate File Hub includes optional Windows File Explorer integration.

After installing the converter integration, supported files can be converted through the right-click menu.

Features include:

- Quick format conversion
- Multiple-file selection
- Mixed video, image, and audio selections
- Same-format repair/re-encoding
- Batch conversion
- Separate conversion settings for each media category
- Cancel support

---

## Automatic Updates

Starting with **v1.2.0**, GL!TCH Ultimate File Hub includes an automatic update system.

When a newer version is published:

1. The application checks the official GitHub Releases page.
2. The installed version is compared with the newest available version.
3. An update notification is displayed.
4. The installer can be downloaded directly through the application.
5. The new installer launches automatically.

Automatic update checking can be enabled or disabled from **Settings**.

There is also a manual **Check for Updates** option.

> Users upgrading from a version older than v1.2.0 must install v1.2.0 or newer manually once before automatic updating becomes available.

---

## Feedback System

The application includes a built-in feedback system.

Users can submit:

- Bug Reports
- Feature Requests
- General Feedback
- Other feedback

Feedback is sent directly through the application's feedback service without requiring the user to open an email program.

---

## Firefox Authentication

Some websites may restrict access to media unless the user is signed in.

When a normal download fails, GL!TCH Ultimate File Hub may recommend retrying with Firefox authentication.

This uses the user's existing Firefox browser session for content they are already authorized to access.

Firefox is not required for normal public downloads.

---

## Twitter / X Support

Twitter/X media extraction can vary because the platform frequently changes how media is delivered.

The application includes additional retry handling for Twitter/X links, including:

- Normal public extraction
- Cleanup of `/video/1` and similar media-specific links
- Base-post retries
- Firefox authentication fallback
- Alternate extraction attempts

For best results, copy the post link using:

**Share → Copy link**

A normal link should resemble:

`https://x.com/username/status/POST_ID`

instead of ending in `/video/1` or `/photo/1`.

Some posts may still be unavailable because of changes or restrictions on Twitter/X itself.

---

## Appearance

The application includes a customizable GL!TCH interface.

Features include:

- Dark interface
- Custom accent color
- Dynamic icon coloring
- Smooth hover effects
- Appearance customization
- Reset to Default Appearance
- Modern main menu
- Optional Legacy Main Menu UI

The selected appearance is saved between sessions.

---

## Folder Settings

Separate output locations can be configured for:

- Downloads
- Compressed files
- Converter tools

Settings are stored in the user's Windows application-data directory rather than inside the installation folder.

---

## Installation

### Recommended Installation

1. Open the latest GitHub Release.
2. Download:

   `GlitchUltimateFileHub-Setup-v1.2.0.exe`

3. Run the installer.
4. Complete setup.
5. Launch **Glitch's Ultimate File Hub**.

[View Releases](../../releases)

---

## System Requirements

- Windows 10 or Windows 11
- 64-bit Windows recommended
- Internet connection for online media downloads and update checking
- Firefox optional for authenticated downloads

Some conversion and download operations can require significant CPU usage depending on resolution, codec, and file size.

---

## Important Notes

Downloads depend on the source website remaining compatible with the underlying extraction tools.

Websites can change their media systems without notice. A download that previously worked may temporarily stop working until compatibility is updated.

Not every output format is available for every source.

---

## Responsible Use

GL!TCH Ultimate File Hub is intended for legitimate personal media and file-management workflows.

Users are responsible for ensuring they have permission to download, convert, store, or redistribute content.

The application should not be used to circumvent access controls or obtain content the user is not authorized to access.

---

## Privacy

Most file conversion and compression operations are performed locally on the user's computer.

Files selected for local conversion or compression are not uploaded by GL!TCH Ultimate File Hub.

Internet access is used when required for features such as:

- Media downloading
- Update checking
- Feedback submission

---

## Version

### Current Version

**v1.2.0**

Version information is also displayed directly on the main screen of the application.

---

## Developer

Developed by **Gl!tch Studios**.

---

## License

See the included `LICENSE` file for licensing information.
