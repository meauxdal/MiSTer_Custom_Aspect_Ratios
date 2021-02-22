**Update: Automatic vertical+horizontal integer scaling has been [officially added](https://misterfpga.org/viewtopic.php?p=19033#p19033) to several popular cores. This option will supersede most of the function of this repository in an easier-to-use way, so please prefer this option when possible.**

# MiSTer Custom Aspect Ratios

Drop-in custom aspect ratios for various cores for the MiSTer FPGA platform. Use with vscale_mode=1* for the purpose of achieving both vertical and horizontal integer aspect scaling, minimizing aspect ratio error when possible. Most of these ratios have been generated using Rysha's aspect ratio calculator, converted to a web app by morf77: https://morf77.pythonanywhere.com/ar

These ratios are intended for use along with vscale_mode=1* in order to avoid inconsistently scaled pixels. This avoids shimmering when scrolling along both the vertical and horizontal axes, usually at the expense of some aspect ratio accuracy.

*Note that the 1080p5x.txt ratios are an exception to this and require vscale_mode=0. See 1080p5x.txt for appropriate .ini settings.

# Updates

Follow this [thread](https://misterfpga.org/viewtopic.php?f=31&t=1991&p=17826#p17826) on the MiSTer FPGA forums for updates.

# Instructions

Set vscale_mode=1 either globally or for the relevant core in MiSTer.ini or an alt .ini file.

Check the .txt file for your desired default video_mode (720p.txt for video_mode=0, 1080p.txt for video_mode=8, 1440p.txt for video_mode=12). Copy the core header and desired ratios to the .ini file and then set the ratio by adjusting the Aspect Ratio within the core.

1200p.txt is intended for custom video_modes. Two examples are given below:

```
video_mode=1920,48,32,80,1200,3,6,26,154128
; 1920x1200@60Hz
```

```
video_mode=1600,64,192,304,1200,1,3,46,162000
; 1600x1200@60Hz
```

[*Example modelines courtesy atrac17*](https://misterfpga.org/viewtopic.php?p=4654#p4654)

There are comments indicating base resolution, pixel clock used, NTSC or PAL, unreduced pixel aspect ratio, core video settings, and example games. As of February 6, 2021, the MiSTer framework only allows you to specify 2 custom aspect ratios per core in addition to 2 global ratios (with each .ini file having its own set), so you'll need to determine which ones you want to use and adjust the .ini accordingly before launching the core.

*1080p5x.txt contains ratios intended for use with builds which have enabled vertical cropping in order to allow 5x vertical integer scaling at 1080p. Per sorgelig:*

> In audio & Video page you will find Vertical Crop option. This option is enabled only when all following conditions are met:
>
> - Resolution is 1920x1080.
> - vscale_border isn't used (or vscale_border=0) in MiSTer.ini
> - vscale_mode isn't used (or vscale_mode=0) in MiSTer.ini
> - forced_scandoubler=0 in MiSTer.ini
> - In OSD menu Scandoubler Fx: None

*Other .txt files correspond to other custom video_modes. Files beyond the main four (720p.txt, 1080p.txt, 1200p.txt, 1440p.txt) may be less comprehensive.*

# Issues

Some especially wide aspect ratios have issues with video_mode=12 (1920x1440@60, or 1440p.txt here) due to exceeding 1920 pixels in width. If you attempt to set a custom aspect ratio that exceeds the horizontal resolution, you may see a resolution change. You can use a custom video_mode (or video_mode=13, if suitable) for ratios that exceed this resolution. You may encounter similar issues at 1600x1200 resolution using the 1200p.txt ratios.

# Notes

The relevant .ini file must be saved before the core is loaded or the custom aspect ratios will not appear. If you use 2 custom aspect ratios, check that one is labeled custom_aspect_ratio_1 and the other custom_aspect_ratio_2 to ensure both are selectable.

_Currently per-core custom aspect ratios seem to override global custom aspect ratios._

_Custom aspect ratios only work in cores that have been updated to enable the function._

These ratios have been generated using mostly default core settings. Settings that influence resolution and aspect ratio are commented when possible.

For consoles, assume NTSC for now. PAL modes may need special consideration depending on core.

Not all ratios have been tested, especially those at 1080p and 1200p.

Most ratios were calculated using morf77's online aspect ratio calculator based on code by Rysha. Without this calculator I wouldn't have been able to calculate these!

# Resources & Links

https://morf77.pythonanywhere.com/ar - Rysha's aspect ratio calculator, converted to a web app by morf77

https://pineight.com/mw/?title=Dot_clock_rates - various pixel clocks

http://www.geocities.ws/podernixie/htpc/modes-en.html - more pixel clocks and information

http://www.spritesmind.net/retro/2VGA/2VGA.html - additional information on portable systems

https://misterfpga.org/ - MiSTer FPGA forums

https://misterfpga.org/viewtopic.php?f=33&t=149 - custom video modes thread on MiSTer FPGA forums

https://misterfpga.org/viewtopic.php?f=31&t=1899 - morf77's aspect ratio calculator discussion thread on MiSTer FPGA forums

https://misterfpga.org/viewtopic.php?f=31&t=1863 - dfilskov's thread with additional aspect ratios on MiSTer FPGA forums

https://misterfpga.org/viewtopic.php?f=31&t=1991 - my thread for this project on MiSTer FPGA forums
