# Command & Conquer Generals - Zero Hour and Online
Instructions on how to run Generals Zero Hour and Generals Online on CachyOS using Lutris and Wine 

## Installation
To Install Generals Zero Hour followo the following steps. I'm using an iso that contains both Generals and Generals - Zero Hour install.

### 1. Mount the iso
Assumes that the Zero Hour iso is in the Downloads folder
```
mkdir -p ~/iso-zerohour
sudo mount -o loop ~/Downloads/Copy\ of\ C\&C\ Generals\ -\ Zero\ Hour.iso ~/iso-zerohour
```

### 2. Install on Lutris
2.1 Start Lutris  
2.2 Press on '+' at top left to add a game  
2.3 Select 'Install a Windows game from an executgable'  
2.4 Give it the name 'Command & Conquer Generals - Zero Hour', leave the identifier as is.  
2.5 Press on the 'Install' button on the option 'Setup file'.  
2.6 Select the 'setup.exe' from the mounted ISO.  
2.7 Follow the install process to the end.

### 3. Install Winetricks items
One thing to note is the WINEPREFIX is dependent on where you keep/install your lutris games. In the following, you can substitute your home directory with the username you have.
```
WINEPREFIX="/home/<username>/Games/<your-command-conquer-generals-zero-hour-install-folder>/" winetricks vcrun2005 vcrun2008 vcrun2010 vcrun2019 d3dx9 corefonts directplay dotnet48
```

### 4. Create options.ini
You can try to run the game at this point, but if you want to complete the setup, create the files
```
~/Games/<your-command-conquer-generals-zero-hour-install-folder>/drive_c/users/steamuser/Documents/Command\ and\ Conquer\ Generals\ Zero\ Hour\ Data/Options.ini
~/Games/<your-command-conquer-generals-zero-hour-install-folder>/drive_c/users/steamuser/Documents/Command\ and\ Conquer\ Generals\ Data/Options.ini
```
with contents:
```
AntiAliasing = 0
BuildingOcclusion = yes
CampaignDifficulty = 0
DrawScrollAnchor =
DynamicLOD = yes
ExtraAnimations = yes
GameSpyIPAddress = 0.0.0.0
Gamma = 50
IPAddress = 0.0.0.0
IdealStaticGameLOD = High
LanguageFilter = false
MoveScrollAnchor =
MusicVolume = 50
Resolution = 1920 1080
Retaliation = yes
SFX3DVolume = 79
SFXVolume = 71
ScrollFactor = 50
SendDelay = no
StaticGameLOD = High
UseAlternateMouse = no
VoiceVolume = 70
```

### 5. File Cleanup
Make sure the following file doesn't exist, if it exist, ename it or delete it.
```
~/Games/<your-command-conquer-generals-zero-hour-install-folder>/drive_c/Program Files (x86)/R.G. Mechanics/Command and Conquer - Generals/Command and Conquer Generals Zero Hour/Data/INI/INIZH.big
```

### 6. Remove/Rename dbghelp.dll
```
~/Games/<your-command-conquer-generals-zero-hour-install-folder>/drive_c/Program Files (x86)/R.G. Mechanics/Command and Conquer - Generals/Command and Conquer Generals Zero Hour/dbghelp.dll
~/Games/<your-command-conquer-generals-zero-hour-install-folder>/drive_c/Program Files (x86)/R.G. Mechanics/Command and Conquer - Generals/Command and Conquer Generals/dbghelp.dll
```
### 7. Download Genneral Online and GenLauncher
7.1 [Generals Online](https://www.playgenerals.online/#download) - download [link](https://cdn.playgenerals.online/GeneralsOnline_setup_032926_QFE5.exe)  
7.2 [GenLauncher](https://www.moddb.com/mods/genlauncher/downloads/genlauncher1009) - download [link](https://www.moddb.com/downloads/start/277509). This is a zip file, extract the .exe from it.  
7.3 GenLauncherGo - download [link](https://www.playgenerals.online/download/GenLauncherGO.exe)  
7.4 [GenTool](https://www.gentool.net/) - download [link](https://www.gentool.net/download/GenTool_v8.9.exe)

### 8. Install GenTool & Genrals Online
8.1 Copy `GenTool_v8.9.exe` and `GeneralsOnline_setup_032926_QFE5.exe` to `/home/<username>/Games/<your-command-conquer-generals-zero-hour-install-folder>/`
8.2 `cd` into `/home/<username>/Games/<your-command-conquer-generals-zero-hour-install-folder>/`
8.3 Run the following command and let the installation complete.
```
WINEPREFIX="/home/<username>/Games/<your-command-conquer-generals-zero-hour-install-folder>/" wine GenTool_v8.9.exe
```
8.4 Run the following command.
```
WINEPREFIX="/home/<username>/Games/<your-command-conquer-generals-zero-hour-install-folder>/" wine GeneralsOnline_setup_032926_QFE5.exe
```
8.5 It will ask you where **Zero Hour** binary is found. Select `~/Games/<your-command-conquer-generals-zero-hour-install-folder>/drive_c/Program Files (x86)/R.G. Mechanics/Command and Conquer - Generals/Command and Conquer Generals Zero Hour/generals.exe` and let the installation complete.

### 9. Copy Generals Online Launchers
Copy `GenLauncherGO.exe` and `GenLauncher.exe` to the install folder here `~/Games/<your-command-conquer-generals-zero-hour-install-folder>/drive_c/Program Files (x86)/R.G. Mechanics/Command and Conquer - Generals/Command and Conquer Generals Zero Hour/`.

## Running The Game
**NOTE**: These are steps the need to be run the directory `~/Games/<your-command-conquer-generals-zero-hour-install-folder>/drive_c/Program Files (x86)/R.G. Mechanics/Command and Conquer - Generals/Command and Conquer Generals Zero Hour/` so cd into before running the commands.

### GenLauncher
You need to run the following in the above mentioned directory otherwise the mods will not be installed and it will hang at 'Preparing. Please wait ...'
```
WINEPREFIX="/home/<username>/Games/<your-command-conquer-generals-zero-hour-install-folder>/" wine GenLauncher.exe
```
Or
```
WINEPREFIX="/home/<username>/Games/<your-command-conquer-generals-zero-hour-install-folder>/" wine GenLauncherGO.exe
```
