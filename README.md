# MiSTer_Custom_Aspect_Ratios
Drop-in custom aspect ratios for various cores for the MiSTer FPGA platform. Use with vscale=1 for the purpose of achieving both vertical and horizontal integer aspect scaling, minimizing aspect ratio error when possible. Most of these ratios have been generated using Rysha's aspect ratio calculator, turned into a web app by morf77: https://morf77.pythonanywhere.com/ar

These ratios are intended for use along with vscale=1 in order to avoid inconsistently scaled pixels. The avoids shimmering when scrolling along both the vertical and horizontal axes at the expense of aspect ratio accuracy.

**Instructions**

Set vscale=1 either globally or for the relevant core.

Check the .txt file for your desired default video_mode (720p.txt, 1080p.txt, 1200p.txt, 1440p.txt). Copy the core header and desired ratios to MiSTer.ini or an alt .ini file and then set the ratio by adjusting the Aspect Ratio within the core.

There are comments indicating core video settings, pixel clocks, resolutions, and relevant games. As of February 6, 2021, the MiSTer framework only allows you to specify 2 custom resolutions per core (with each .ini file having its own set), so you'll need to determine which ones you want to use and adjust the .ini accordingly before launching the core.

**Issues**

Some especially wide aspect ratios have issues with video_mode=12 (1920x1440@60, or 1440p.txt here) due to exceeding 1920 pixels in width. If you attempt to set a custom aspect ratio that exceeds the horizontal resolution, you may see a resolution change. You can use a custom video_mode (or video_mode=13, if suitable) for ratios that exceed this resolution.

**Notes**

The relevant .ini file must be saved before the core is loaded or the custom aspect ratios will not appear. If you use 2 custom aspect ratios, check that one is labeled custom_aspect_ratio_1 and the other custom_aspect_ratio_2 to ensure both are selectable.

Custom aspect ratios only work in cores that have had the function enabled in the framework.

These ratios have been generated using mostly default core settings. Settings that influence resolution and aspect ratio are commented when possible.

For consoles, assume NTSC for now. PAL games may need special consideration depending on core.

Not all ratios have been tested, especially those at 1080p and 1200p.

Most ratios were calculated using morf77's online aspect ratio calculator based on code by Rysha. Without this calculator I wouldn't have been able to calculate these!

**Resources**

https://morf77.pythonanywhere.com/ar - Rysha's aspect ratio calculator, turned into a web app by morf77

https://pineight.com/mw/?title=Dot_clock_rates - various pixel clocks

http://www.geocities.ws/podernixie/htpc/modes-en.html - more pixel clocks and information

http://www.spritesmind.net/retro/2VGA/2VGA.html - additional information on portable systems

https://misterfpga.org/viewtopic.php?f=31&t=1899 - morf77's aspect ratio calculator discussion thread on MiSTer FPGA forums

https://misterfpga.org/viewtopic.php?f=31&t=1863 - dfilskov's thread with additional aspect ratios on MiSTer FPGA forums

https://misterfpga.org/viewtopic.php?f=31&t=1991 - my thread for this project on MiSTer FPGA forums
