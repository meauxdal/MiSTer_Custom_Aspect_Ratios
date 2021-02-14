https://www.patreon.com/posts/47525249
by atrac17

FEB 14, 2021 AT 6:58 AM
Sega MegaDrive, MegaCD, Mark III, and GameGear Core(s) 5x Custom Modelines for MiSTerFPGA
Sega MegaDrive, MegaCD, Mark III, and GameGear Core(s) for MiSTerFPGA
Attached are video modelines for 5x/6x/8x integer scaling with custom aspect ratio's for the Sega console core(s) currently available for MiSTer. Once again, I'm not an expert but wanted to share my findings fore these cores on a 4k panel. 

The custom aspect ratio's provided look decent. My preference is AR=49:48 for MegaDrive and AR=50:49 for MegaCD. From my findings, these will work on most 4k displays. They've been extensively tested on LG CX, C9, B6, E9, UM7300, and UN7300 models. They will also work on a LG 32GK650F-B 1440p monitor.

These are my recommended filters. This is subjective and preference is up to the end user.

SL_Br_110_020_Sharp
SL_Br_110_030_Sharp
SL_Br_110_040_Sharp
SL_Br_110_050_Sharp
LCD_Effect_05 (GameGear Only)
Poly 2.7
Resolution for MegaDrive/MegaCD

Native Resolution:     256x224@59.922751013551Hz
Native Resolution:     320x224@59.922751013551Hz
ASCAL Resolution:   1280X1120@59.922751013551Hz
Aspect Ratios for MegaDrive/MegaCD

AR=4:3   (Original; bordered due to modeline, DO NOT USE)
AR=8:7   (Full Screen 5x; this is the exact PAR per the pixel clock for 256 mode)
AR=32:35   (Full Screen 5x; this is the exact PAR per the pixel clock for 320 mode)
AR=49:48   (Custom Aspect Ratio taken from github; 1225x1200 forced into a 1120 vertical frame)
AR=50:49   (Custom Aspect Ratio taken from github; 1250x1225 forced into a 1120 vertical frame)
AR=117:112   (1170x1120 Custom Aspect Ratio; use in 320 mode - 1280*32:35)
























These are shots from an LG CX (6) and LG UM7300 (5).



Resolution for Mark III/GameGear

Native Resolution:     256x192@59.922751013551Hz (6x for MarkIII)
Native Resolution:     160x144@59.922751013551Hz (8x for GameGear)
ASCAL Resolution:   1536X1152@59.922751013551Hz
Aspect Ratios for Mark III

AR=4:3   (Original; this is the exact DAR for 256x192)
AR=4:3   (Full Screen 6x; this is the exact DAR for 256x192)
AR=27:26   (Custom Aspect Ratio taken from github; 1225x1200 forced into a 1152 vertical frame)
AR=8:7   (Custom Aspect Ratio; this is the exact PAR for 256x192)
AR=14:9   (Custom Aspect Ratio; 1820x1170/256x192 for CRT in 4:3 forced into a 1152 vertical frame)


Aspect Ratios for GameGear

AR=4:3   (Original; this is the exact DAR for per the pixel clock)
AR=4:3   (Full Screen 6x; this is the exact DAR for 1536x1152)
AR=27:26   (Custom Aspect Ratio taken from github; 1225x1200 forced into a 1152 vertical frame)
AR=8:7   (Custom Aspect Ratio; this is the exact PAR for 160x144)
AR=10:9   (Custom Aspect Ratio; this is the exact DAR for 160x144)




































These are shots from an LG CX (7) and LG UM7300 (10).



Basic Information
These modelines are designed to be utilized on LCD/LED/OLED "television" displays. These are not designed for monitors that do not have a scaling function built-in. The intent is to use the ASCAL scaler on the MiSTer to scale 4/5x horizontal (256/320) and 5x vertical or 6x integer/8x integer utilizing the displays scaler.

Your display will then scale the resolution in integer increments and fill the bezel vertically. Utilizing the custom aspect ratio settings the MiSTer can control the horizontal resolution being displayed.

MegaDrive/MegaCD
When sending 1280x1120, I used "Original" or "4:3" aspect ratios on the display. This is why I have chose to not utilize straight 5x integer scaling to the display. When 1600x1120 is utilized it forces using "16:9" on the display.

Depending upon the core, this changes how "Original" and "Full Screen" function with aspect ratio's on MiSTer and vice versa with "16:9", "Original", and "4:3" on the display "television". Also, 1280x1120 is 8:7, 4:5 PAR (1280:1120). This is what the "Full Screen" setting will achieve in the MiSTer OSD.


Mark III/GameGear
When sending 1536x1152, I used "Original" or "4:3" aspect ratios on the display. This is why I have chose to not utilize straight 5x integer scaling to the display. Also, 1536x1152 is 48:35, 6:5 PAR (1536:1152). This is what the "Full Screen" setting will achieve in the MiSTer OSD.





For end user compatibility I have chosen to use 4x horizontal and 5x vertical modelines (6x/8x for Mark III/GameGear) in the interim. I have ordered an LG CX and will provide 6x resolutions further down the road. I will publish modelines and custom aspect ratio's for other arcade cores and consoles in the coming days.

If you use a fixed display or it isn't compatible you can replace the modeline provided in the attachments with these. Just use "replace all" in a text editor.

1600,48,32,80,1120,3,10,19,121651 (MegaDrive/MegaCD)
1920,48,32,80,1152,3,7,23,147888 (Mark III/GameGear)
AR=8:7   (New Custom Aspect Ratio for 5x if replacing 1280x1120)
AR=48:35   (New Custom Aspect Ratio for 6x/8x if replacing 1536x1152)
Thanks to all my beta testers!!! I will be posting official Neo Geo (MVS) modelines later this afternoon. Please disregard my previous twitter posts regarding MVS!
