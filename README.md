# CompressEasy (Martin Eesmaa)

CompressEasy can compress your big files into compressed file, includes video, audio and more.

On 1st June 2022, CompressEasy is not yet ready, but you can have look an source code and doc in README.md

# Supported compressed (compatability on Windows)

Windows 3.1: BMP, AVI (Microsoft RLE/Video 1, Indeo Video & Cinepak), WAV, (external available of MP3, ZIP, MPG (MPEG-1, MPEG-2))

Windows 2000:

# Video codecs availability

Windows | Cinepak | Microsoft Video 1 | Indeo Video | Microsoft RLE | MPEG-1 | MPEG-2 | MP43 | MP4S | AP41 | WMV7 | WMV8 | WMV9 | XVID | SWF | VP6 | VP8 | VP9 | AVC | HEVC | AV1
------- | --- | --------- | --------- | --------- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
Media Player 3.1 / Windows 3.x | :x: | :white_check_mark: | :x: | :white_check_mark: | ⚠️ | ⚠️ | :x: | :x: | :x: | :x: | :x: | :x: | :x: | ⚠️ (3) | :x: | :x: | :x: | :x: | :x: | :x: |
Media Player 3.15 / Windows 3.x | :white_check_mark: | :white_check_mark: | :white_check_mark: | :white_check_mark: | ⚠️ | ⚠️ | :x: | :x: | :x: | :x: | :x: | :x: | :x: | ⚠️ (3) | :x: | :x: | :x: | :x: | :x: | :x: |
Media Player 6.1 | :white_check_mark: | :white_check_mark: | :white_check_mark: | :white_check_mark: | ⚠️ | ⚠️ | :x: | :x: | :x: | :x: | :x: | :x: | :x: | ⚠️ | :x: | :x: | :x: | :x: | :x: | :x: |
Media Player 6.4 | :white_check_mark: | :white_check_mark: | :white_check_mark: | :white_check_mark: | :black_square_button: | ⚠️ | :x: | :x: | :x: | :x: | :x: | :x: | :x: | ⚠️ | :x: | :x: | :x: | :x: | :x: | :x: |
Media Player 7.0 | :white_check_mark: | :white_check_mark: | :white_check_mark: | :white_check_mark: | :white_check_mark: | :white_check_mark: | :white_check_mark: | :white_check_mark: | ⚠️ | :white_check_mark: | :x: | :x: | :x: | ⚠️ | :x: | :x: | :x: | :x: | :x: | :x: |
Media Player 7.1 | :white_check_mark: | :white_check_mark: | :white_check_mark: | :white_check_mark: | :white_check_mark: | :white_check_mark: | :white_check_mark: | :white_check_mark: | ⚠️ | :white_check_mark: | :white_check_mark: | :x: | ⚠️ | ⚠️ | ⚠️ | :x: | :x: | :x: | :x: | :x: |
Media Player 8.0 | :white_check_mark: | :white_check_mark: | :white_check_mark: | :white_check_mark: | :white_check_mark: | :white_check_mark: | :white_check_mark: | :white_check_mark: | ⚠️ | :white_check_mark: | :white_check_mark: | :x: | ⚠️ | ⚠️ | ⚠️ | :x: | :x: | :x: | :x: | :x: |
Media Player 9.0 | :white_check_mark: | :white_check_mark: | :white_check_mark: | :white_check_mark: | :white_check_mark: | :white_check_mark: | :white_check_mark: | :white_check_mark: | ⚠️ | :white_check_mark: | :white_check_mark: | :white_check_mark: | ⚠️ | ⚠️ (9) | ⚠️ | :x: | :x: | :x: | :x: | :x: |
Media Player 10.0 | :white_check_mark: | :white_check_mark: | :white_check_mark: | :white_check_mark: | :white_check_mark: | :white_check_mark: | :white_check_mark: | :white_check_mark: | ⚠️ | :white_check_mark: | :white_check_mark: | :white_check_mark: | ⚠️ | ⚠️ | ⚠️ | :x: | :x: | :x: | :x: | :x: |
Media Player 11.0 | :white_check_mark: | :white_check_mark: | :white_check_mark: | :white_check_mark: | :white_check_mark: | :white_check_mark: | :white_check_mark: | :white_check_mark: | ⚠️ | :white_check_mark: | :white_check_mark: | :white_check_mark: | ⚠️ | ⚠️ | ⚠️ | :x: | :x: | :x: | :x: | :x: |
Media Player 12.0 | :white_check_mark: | :white_check_mark: | :white_check_mark: | :white_check_mark: | :white_check_mark: | :white_check_mark: | :white_check_mark: | :white_check_mark: | :white_check_mark: | :white_check_mark: | :white_check_mark: | :white_check_mark: | :white_check_mark: | ⚠️ | ⚠️ | ⚠️ |

:white_check_mark: = Ready to play, compatible

⚠️ = Needs required codec or external program to play video codec.

:x: = Not compatible

:black_square_button: = Not tested yet

We strong recommend using VLC or MPV to play your media file, starting Windows XP and later.

# Stream companies

Most stream companies use x264 than MPEG-2, so the customers don't have to download, no lossless, good stream compatability for TV friendly.

### Estonian Public Broadcasting (Eesti Rahvusringhääling)

The company uses x264 version: x264 core 160 r3000 33f9e14

1080p (FHD):

```
ffmpeg -i naiteks.mp4 -c:v libx264 -x264-params "nal-hrd=none" -x264opts keyint=50:min-keyint=26:scenecut=0 -b:v 3M -maxrate 3M -bufsize 9M -r 25 -vf scale=1920:1080 -pix_fmt yuv420p -color_primaries bt709 -color_trc bt709 -colorspace bt709 -color_range tv -c:a aac -ac 2 -ar 48000 -b:a 128k kokkuvote.mp4
```

720p (HD):

```
ffmpeg -i naiteks.mp4 -c:v libx264 -x264-params "nal-hrd=none" -x264opts keyint=50:min-keyint=26:scenecut=0 -b:v 1.5M -maxrate 1.5M -bufsize 6M -r 25 -vf scale=1280:720 -pix_fmt yuv420p -color_primaries bt709 -color_trc bt709 -colorspace bt709 -color_range tv -c:a aac -ac 2 -ar 48000 -b:a 128k kokkuvote.mp4
```

396p (SD):

```
ffmpeg -i naiteks.mp4 -c:v libx264 -x264-params "nal-hrd=none" -x264opts keyint=50:min-keyint=26:scenecut=0 -b:v 1M -maxrate 1M -bufsize 3M -r 25 -vf scale=704:396 -pix_fmt yuv420p -color_primaries bt709 -color_trc bt709 -colorspace bt709 -color_range tv -c:a aac -ac 2 -ar 48000 -b:a 128k kokkuvote.mp4
```

More coming soon...

- Martin Eesmaa
