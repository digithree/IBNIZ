# IBNIZ_D3

## Licence

Original project “IBNIZ” code by Ville-Matias Heikkila viznut@low.fi
Original licence zlib licence (see src/orig_licence.txt)
The original author is not liable for this derivative

This version is licenced under the GPL v3 licence, (see src/licence.txt)

## New features and changes

### Video output

Working video output to file is a priority. So far this works but with a ~~very low~~ **now improved** framerate, depending on how much work the virtual machine is doing, i.e. the complexity of the current program.

The the following to output live to a file vid.avi with no audio:

```bash
./ibniz -a -M | ffmpeg -y -i - -r 30 -vcodec h264 vid.avi
```

If you what higher quality you can specify the bitrate, for example 2mb bitrate:

```bash
./ibniz -a -M | ffmpeg -y -i - -r 30 -vcodec h264 -b 2000k vid.avi
```

Note also that there is some timing discrepancy between the realtime video stream and the video playback speed - the video is faster, i.e. skipping frames. I think that the virtual machine will need to be optimised to get higher framerate output.

### Misc changes

Additionally:

1. Added the commandline flag -a to turn off audio output.
2. Stopped out of the the virtual machine monitor information on the bottom of the screen EXCEPT the frames per minute, this is for this current debug version
3. Changed the font colour to dark grey in order to make live coding less conspicuous EXCEPT for the fps display

## What about the rest?

Please look at Viznut’s original introduction in src/ibniz.txt