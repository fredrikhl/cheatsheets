# ffmpeg

## inspect `<file>`

```bash
ffmpeg -i <file>
```

## image ↔ video

```
# image sequence <prefixN.jpg> → video
ffmpeg -f image2 -i <prefix%d.jpg> <outfile>

# video → image sequence
ffmpeg -i <infile> <prefix%4d.jpg>

# video → gif
ffmpeg -i <infile> <outfile.gif>
ffmpeg -i <infile> -pix_fmt rgb24 -r 25 -s 200x100 -ss 00:00:05.200 -t 00:00:03 <outfile>
```

Supported formats: pgm, ppm, pam, pgmyuv, jpeg, gif, png, tiff, sgi


## re-encode a video in a specific format

```bash
ffmpeg -i <infile> <outfile>
```

* Audio codec: aac
* Audio bitrate: 128kb/s
* Video codec: mpeg4
* Video bitrate: 1200kb/s
* Video size: 320x180

```bash
ffmpeg -i <infile> input \
       -acodec aac -ab 128kb \
       -vcodec mpeg4 -b 1200kb \
       -mbd 2 -flags +4mv+trell -aic 2 -cmp 2 -subcmp 2 \
       -s 320x180 \
       -title <Title> \
       <outfile.mp4>
```


## extract audio from video

* Audio codec: mp3
* Audio sample rate: 44.1kHz
* Audio bitrate: 192 kbps

```bash
ffmpeg -i <infile> -vn -ar 44100 -ac 2 -ab 192 -f mp3 <outfile.mp3>
```

## combine video and audio

```bash
ffmpeg -i <if>.wav -i <if> <of>
```

## using bchunk to split audio using a cue file

```bash
ffmpeg -i file.ape file.wav
bchunk -w file.cue file.wav prefix
```

## add time to end of video

Command uses a "nullsrc" video as base, and our source video as "overlay". The
overlay filter will "freeze" the overlay when the duration of the nullsrc video
is longer.

Source video with resolution (1376x1024), duration (30s), and framerate (10
fps): `nullsrc=s=1376x1024:d=30:r=10`

Overlay filter: `[0:v][1:v]overlay[video]`

Assign first input as base layer, and second video as overlay:

```bash
ffmpeg -f lavfi \
       -i nullsrc=s=1376x1024:d=30:r=10 \
       -i infile.mp4 \
       -filter_complex "[0:v][1:v]overlay[video]" \
       -map "[video]" -an -shortest \
       outfile.mp4
```


## alter speed / framerate

### video
```bash
# e.g. double speed with setpts (factor 0.5):
ffmpeg -i input.mkv -filter:v "setpts=0.5*PTS" output.mkv
# modify framerate with `-r <framerate>` to prevent framedrop
```

### audio
```bash
# e.g. quadruple speed with atempo (factor 4.0):
ffmpeg -i input.mkv -filter:a "atempo=2.0,atempo=2.0" -vn output.mkv
# the atempo filter must be [0.5, 2.0], but we can repeat it
```

### both
```bash
# filter both audio and video with `filter_complex`:
ffmpeg -i input.mkv \
       -filter_complex "[0:v]setpts=0.5*PTS[v];[0:a]atempo=2.0[a]" \
       -map "[v]" -map "[a]" \
       output.mkv
```


## filter primer

```bash
# video filter
ffmpeg -i infile -filter:v "<filter>" outfile
ffmpeg -i infile -vf "<filter>" outfile

# audio filter

ffmpeg -i infile -filter:a "<filter>" outfile
ffmpeg -i infile -af "<filter>" outfile

# scale
# fix odd number resolution issue with scaling
ffmpeg -i infile \
       -filter:v "scale=trunc(iw/2)*2:trunc(ih/2)*2" \
       outfile

# crop video to width and height, starting at position x,y
ffmpeg -i infile \
       -filter:v "crop=width:height:x:y" \
       outfile
```
