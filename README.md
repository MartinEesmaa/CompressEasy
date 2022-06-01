# CompressEasy (Martin Eesmaa)

CompressEasy can compress your big files into compressed file, includes video, audio and more.

On 1st June 2022, CompressEasy is not yet ready, but you can have look an source code and doc in README.md

# Supported compressed (compatability on Windows)

Windows 3.1: BMP, AVI (Microsoft RLE/Video 1, Indeo Video), WAV (available MP3, ZIP, MPG (MPEG-1, MPEG-2))

# Stream companies

Most stream companies use x264 than MPEG-2, so the customers don't have to download, no lossless, good compatability for TV friendly.

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