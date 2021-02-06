# MiSTer_Custom_Aspect_Ratios
Drop-in custom aspect ratios for various cores for the MiSTer FPGA platform.

Check the file for your desired default video_mode (720p, 1080p, 1200p, 1400p). Copy the core headers and desired ratios to your MiSTer.ini or an alt .ini file and then set the ratio by adjusting the Aspect Ratio within the core. 

There are comments indicating core video settings, pixel clocks, resolutions, and relevant games, so be sure to check those out to see which ones you need. As of February 6, 2021, the MiSTer framework only allows you to specify 2 custom resolutions, so you'll need to determine which ones you want to use and adjust the .ini accordingly before launching the core.
