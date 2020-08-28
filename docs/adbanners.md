Ad Banners
Configuration File
The configuration file consists of a single array named ads which can contain an unlimited number of elements. Each element contains 4 pairs in the following order: filename, url, client, and lang.

filename: A string containing the filename of the ad banner, should not include a path.
url: A string containing the URL that users should be directed to when clicking on the ad banner.
client: A string containing the 4 character client tag that the ad banner should be shown to, a string of "NULL" will cause the ad banner to be shown to any client.
lang: A string containing a 4 character language code that will be displayed to users who have enabled that particular language, a string of "any" will cause the ad banner to be shown to any user. (e.g. deDE for German, enUS for English)
File Formats
Client	Banner Format
StarCraft	PCX, SMK
Diablo 2	?
WarCraft 2	PCX
WarCraft 3	SMK, MNG, PNG
Banner Dimensions
The dimensions for ad banners are 468 x 60 pixels
How To Create SMK Files
Download the Old Smacker Tools(this only works on Windows XP)
Run smackerw.exe and then click on the Smack (compress) a graphics file.
On the left side, navigate to the folder where your ad banner is stored and select it.
Under Options, click on the Palette tab. Check Total palette colors to use:, set it to 64 and check Starting palette index to use:, set it to 32.
Set 8-bit input palettes to Create new.
Click on the Frame tab and check Create ring?
Smack!
Notes
It is not known how to create PCX files that will display properly in PvPGN