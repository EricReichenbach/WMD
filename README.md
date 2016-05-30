# WMD (Wad Manager for Doom)

WMD is a small  project I started to easily launch Doom wads and play easily.

The project went further than I expected so I decided to share it.

## Main features
- easy to use
- no installation, everything is done in the starting folder (by default where the .exe is)
- saves data in easily readable XML (I don't recommend manually editing it, unless you know what you're doing)
- Drag and drop wad, pk3, pk7...
- Work with any zDoom-like sourceport
- leverage as much as possible sourceport features
 - if no config files are detected, starts the game at the monitor width and height
 - encourages users to create a DOOMWADDIR env variable through a UI
 - allows custom launch parameters on top of the ones generated by the app
- Creation of packs of wads with:
 - Sort order management
 - Separate Save folders
 - Separate Config files
   - Separate Key mapping
   - Separrate Settings
 - source port association
 - can be prepared in a zip file and shared (see the "How to cook a pack" section)

[alt Screenshot](./readme/WMD.png "Screenshot")

## Requirements

Dotnet 4.5 redist, if you are on Windows 10 you should be OK. In any case you can get it there https://www.microsoft.com/en-us/download/details.aspx?id=30653

## How to cook a pack
You can create pack with

- a zdoom-like config file
- multiple wads
- a load order
- saves

To create a pack you just have to follow those instructions:

    ./WMD/ #Wads go here
    ./WMDCONF/ #The config file goes here, must be named [Pack Name].ini (you might want to look into what you are sharing in that ini file)
    ./WMDSAVE/[Pack Name]/ #Saves go here
    ./WMF.xml

in the WMF.xml file should look like that:

    <Wadpack name="[Pack Name]">
    <Wad loadorder="1">.\WMD\[One for each wad]</Wad>
    <Wad loadorder="0">.\WMD\[One for each wad]</Wad>
    </Wadpack>

Once it's okay, zip it (the WMF.xml must be at the root of the archive) and change the .zip extension by .dwp

Now you just have to drag and drop the file in the drap/drop area of the app for the magic to happen.

### DO NOT SHARE A WAD IF YOU ARE NOT THE AUTHOR

If you want to share your config file for a rad wad you just found on doom-world, don't steal the wad.

Just create the xml file with the references to the wads, create your config file, and tell the users to download the wads by themselves, don't put the wads in the archive (it's stealing if you do. You wouldn't steal a car, would you?).

## Contributions

If you want to improve that god awful readme, don't hesitate.

If you have request features go on, but don't expect anything, but if your idea is great I might listen, I don't to bloat the software.
