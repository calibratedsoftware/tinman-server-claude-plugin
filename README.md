# Claude Plugin for Tin Man Server

A plugin that connects [Tin Man Server](https://calibratedsoftware.com) to Claude and Claude Code, giving Claude direct access to professional media tools for film and video production workflows. 

Supports Blackmagic RAW • RED RAW • ARRIRAW • Sony RAW • Apple ProRes RAW • Canon RAW • Licensed Apple ProRes and Avid DNx • MOV/MXF/MP4 formats • Image Sequences — and more.

Available for macOS and Windows.

## Licensing

The **verified copy** and **create thumbnail** tools are currently free to use without a license in Tin Man Server. All other tools operate in demo mode without a Tin Man Server license.

## Requirements

- [Tin Man Server](https://www.calibratedsoftware.com/tin-man-server/) 26.11.5 or later. With an earlier Tin Man, use the plugin release with the same version.
- [Claude](https://claude.ai) (Claude or Claude Code)

## Installation

1. Download the `.zip` for your platform from [Releases](../../releases/latest).
2. Add the plugin to Claude or Claude Code.

## Tools

**tinman-server:scan** — Quick scan of a folder or drive. Returns filename, size, codec, resolution, frame rate, duration, and timecode for every clip.

**tinman-server:query_metadata** — Full metadata extraction. Camera make/model, serial number, firmware, ISO, white balance, tint, shutter angle, lens model, lens serial, aperture, color space, timecode, slate info, and more.

**tinman-server:generate_report** — Generate formatted clip reports with thumbnails. Supports PDF, HTML, JSON, CSV, and XLSX. Report types include clip reports and contact sheets. Configurable dark mode, Rec 709 tonemapping, custom fields, thumbnail count, and HTML asset folder export.

**tinman-server:thumbnail** — Generate JPEG thumbnails from media files. Configurable size, quality, number per clip, and Rec 709 tonemapping.

**tinman-server:export** — Transcode/convert media using 50+ professional presets. ProRes, DNxHD, DNxHR, H.264, H.265, and more. Custom file naming with tokens. Preset overrides for resolution (half, quarter, eighth, max-width, fixed-size), bitrate (H.264/H.265), output colorspace (Rec 709, Rec 709 with tonemapping), and source resizing. GPU export engine support.

**tinman-server:copy** — Verified file copy. Every file checksummed after copy to guarantee integrity.

**tinman-server:cancel** — Gracefully stop a running export or copy.

**tinman-server:generate_config** — Returns the default report configuration template as JSON for customizing reports.

**tinman-server:list_export_presets** — Lists all 50+ available transcode presets.

**tinman-server:validate_file_list** — Checks a JSON file list before it runs: every key and value, and that each path is there.

**tinman-server:file_list_help** — Returns the JSON file list reference: every key, value and color space name.

## JSON File Lists

scan, query_metadata, generate_report, thumbnail, export and copy also take a JSON file list (`file_list`) that gives each folder or clip its own settings in one run: in/out points, export folder and file name, source color space and range, pixel aspect, field order, time base and timecode, rotation and flips, color correction, pre and post CC 3D LUTs, Look with tone mapping, crop and scale, metadata, and audio sync (external audio such as WAV, synced onto video by timecode, in point or out point). copy uses only the list's paths.

Ask Claude for per-clip settings and it builds the list, checks it with validate_file_list, and runs it. A setting a clip can't take is reported, and the rest of the list still runs.

## General Options

These options apply globally to all commands:

- **--gpu-cuda** — Use CUDA instead of OpenCL (Windows/NVIDIA only)
- **--gpu-encode** — Enable GPU export engine (default: CPU)
- **--rawLog** — Set all RAW files to Log
- **--raw709** — Set all RAW files to Rec.709
- **--raw709tonemap** — Set all RAW files to Rec.709 with ToneMapping when available
- **--raw2020** — Set all RAW files to Rec.2020
- **--rawHLG** — Set all RAW files to Rec.2020/HLG
- **--rawPQ** — Set all RAW files to Rec.2020/PQ
- **--rawACES** — Set all RAW files to ACES AP0

## Knowledge

The plugin also includes built-in knowledge that helps Claude understand professional media workflows:

**tinman-server:camera-formats** — Camera brands, RAW formats, codecs, colorspaces, log curves, and LUTs.

**tinman-server:video-workflows** — DIT workflows, on-set data management, dailies, color management, and editorial handoff.

**tinman-server:tinman-server-tools** — Best practices for using the Tin Man tools effectively.

## Links

- [Tin Man Server](https://www.calibratedsoftware.com/tin-man-server/)
- [Tin Man Server User Guide](https://docs.calibratedsoftware.com/tin-man/getting-started-server)
- [Calibrated Software](https://www.calibratedsoftware.com)
