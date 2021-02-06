# MiSTer_Custom_Aspect_Ratios
Drop-in custom aspect ratios for various cores for the MiSTer FPGA platform. Use with vscale=1 for the purpose of achieving both vertical and horizontal integer aspect scaling, minimizing aspect ratio error when possible. Most of these ratios have been generated using https://morf77.pythonanywhere.com/ar.

**Instructions**

Check the .txt file for your desired default video_mode (720p.txt, 1080p.txt, 1200p.txt, 1440p.txt). Copy the core header and desired ratios to MiSTer.ini or an alt .ini file and then set the ratio by adjusting the Aspect Ratio within the core.

There are comments indicating core video settings, pixel clocks, resolutions, and relevant games, so be sure to check those out to see which ones you need. As of February 6, 2021, the MiSTer framework only allows you to specify 2 custom resolutions, so you'll need to determine which ones you want to use and adjust the .ini accordingly before launching the core.

**Issues**

Some especially wide aspect ratios have issues with video_mode=12 (1920x1440@60, or 1440p.txt here) to exceeding 1920 pixels in width. If you attempt to set a custom aspect ratio that exceeds the horizontal resolution, you may see a resolution change. You can use a custom video_mode for ratios that exceed this resolution, but they will likely not work with the default video_mode=12, at least on an LCD display. 

**Notes**

These ratios have been generated using mostly default core settings. Settings that influence resolution and aspect ratio are commented when possible.

Not all ratios have been tested, especially those at 1080p and 1200p.

Most ratios were calculated using morf77's online aspect ratio calculator based on code by Rysha. Without this calculator I wouldn't have been able to calculate these!

**Resources**

https://morf77.pythonanywhere.com/ar - Rysha's aspect ratio calculator, turned into a web app by morfeus_77

https://pineight.com/mw/?title=Dot_clock_rates - various pixel clocks

http://www.geocities.ws/podernixie/htpc/modes-en.html - more pixel clocks and information

http://www.spritesmind.net/retro/2VGA/2VGA.html - additional information on portable systems

https://misterfpga.org/viewtopic.php?f=31&t=1899 - morf77's aspect ratio calculator discussion thread on MiSTer FPGA forums

https://misterfpga.org/viewtopic.php?f=31&t=1863 - dfilskov's thread with additional aspect ratios on MiSTer FPGA forums

https://misterfpga.org/viewtopic.php?f=31&t=1991 - my thread for this project on MiSTer FPGA forums
