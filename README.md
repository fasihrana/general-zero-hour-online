# Command & Conquer Generals - Zero Hour and Online
Instructions on how to run Generals Zero Hour and Generals Online on CachyOS 

## Other Instructions Tried
1. Simplified [here](https://gist.github.com/fasihrana/9ae85c1b4f78a4153421c275bb777598).
2. Steam version [here](https://docs.google.com/document/d/e/2PACX-1vSwYI5JdYH4bWB6WuXOHXNRv8loEtPUABNtGDliMWuQ2QiaLs-Y9mVrH_eHRjvif5SLJfQ9iAJ7mNir/pub).

## Installation
This was tried on POL (PlayOnLinux). POL is not available on pacman, but is available on paru which is a package manager for AUR.

### 1. Download the files
1.1. Generals Zero Hour - download [link](https://dn721806.ca.archive.org/0/items/generals-zero-1.04/Generals%20Zero%201.04.rar)  
1.2. [Generals Online](https://www.playgenerals.online/#download) - download [link](https://cdn.playgenerals.online/GeneralsOnline_setup_032926_QFE5.exe)  
1.3. [GenLauncher](https://www.moddb.com/mods/genlauncher/downloads/genlauncher1009) - download [link](https://www.moddb.com/downloads/start/277509). This is a zip file, extract the .exe from it.  
1.4. GenLauncherGo - download [link](https://www.playgenerals.online/download/GenLauncherGO.exe)  
1.5. [GenTool](https://www.gentool.net/) - download [link](https://www.gentool.net/download/GenTool_v8.9.exe)

### 2. Install
2.1. On POL, click on 'Install a program'  
2.2. Then click 'Install a non-listed program'  
2.3. Click 'Next' on the 'Manual Installation' prompt  
2.4. Select 'Install a program in a new virtual drive'  
2.5. Type a name like 'cc-generals-zh' or something of your liking, then click 'Next'.  
2.6. Click 'Next' without selecting anything on the next screen.  
2.7. Select '64 bits windows installation' and click 'Next'  
2.8. Click 'Browse' and select the `setup.exe` for Generals Zero Hour. It may prompt you for a CD KEY.  
2.9. Click through as prompted to complete the installation.  
2.10. After the installation, it will ask you to Create a shortcut, go to the next section for that.

### 3. Create the Shortcuts
The create shortcut menu lists the following two choices at the top followed by a number of executables that it give you an option for:
a. _'I don't want to make another shortcut'_ (Selecting this and clicking 'Next' will exit the shortcut menu)  
b. _'Browse'_  
3.1. Select 'Browse' and click 'Next'.  
3.2. Click 'Browse'.
3.3. Navigate to 'Program Files (x86)' > 'Command & Conquer Generals Zero 1.04' > 'Command & Conquer Generals Zero Hour'.  
3.4. Select `generals.exe` and click 'Open'.  

### 4. Install the Patches
This is the 'Configure' > 'Miscellaneous' menu  
4.1. On POL, from the games list, select your game but do not run it yet.  
4.2. In the sidebar on the left, click 'Configure'.  
4.3. Click on the 'Miscellaneous' tab.  
4.4. Click 'Run a windows Executable (.exe) file in the virtual drive'.  
4.5. Find the `GenTool_v8.9.exe` and click 'Open' and finish the installation.
4.6. Click 'Run a windows Executable (.exe) file in the virtual drive' again.  
4.7. Find the `GeneralsOnline_setup_032926_QFE5.exe` and click 'Open'

### 5. Copy 'Generals Online' Files
This is the 'Configure' > 'Miscellaneous' menu.  
5.1. Follow steps 4.1 to 4.3.  
5.2. Click 'Open program directory' and make sure it is the 'Command & Conquer Generals Zero Hour' folder. If it is not that folder, that means you created a shortcut for Command & Conquer Generals  executable.  
5.3. Copy `GenLauncherGO.exe` and `GenLauncher.exe` to the directory from step 5.2.  
5.4. To run the `GenLauncher.exe` follow the steps 4.1 to 4.4 then select the file by navigating to the folder you copied it to. This won't work if these excutables are not copied to the 'Command & Conquer Generals Zero Hour' folder.  

### 6. Install wintricks Items
This is the 'Configure' > 'Miscellaneous' menu.    
6.1. Follow steps 4.1 to 4.3.  
6.2. Click on 'Open a shell'.  
6.3. On the command prompt type this `winetricks corefonts allfonts dotnet48` then press enter and click through any menus that popup to complete the installation of these.  

### 7. Shortcuts for Online executables
This is the 'Configure' menu.  
7.1. On POL, from the games list, select your game but do not run it yet.    
7.2. In the sidebar on the left, click 'Configure'.  
7.3. On the menu, in the left sidebar, you will have 'cc_generals_zh' or the name you chose in step 2.5 will be listed, click on that.  
7.4. On the 'General' tab, click 'Make a new shortcut from this virtual drive' and the menu from section **3** will show up.  
7.5. If `GenLauncher.exe` is listed, then select that and click 'Next'.  
7.6. Give it an appropriate name and click 'Next'. This will create an entry under the 'cc_generals_zh' menu from 7.3.  
7.7. It will prompt you for more shortcuts, if you see one for `GeneralsOnlineZH.exe` then repeat the steps 7.5 and 7.6 for it.  

### Problems
1. Framerate mismatch error

## Alternate Installation (not quite working)
**NOTE** This was tried on Lutris and PlayOnLinux, but the iso version did not work.  
To Install Generals Zero Hour on Lutris follow these steps. I'm using an iso that contains both Generals and Generals - Zero Hour install.

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
AntiAliasing = 23
ArchiveReplays = no
BuildingOcclusion = yes
CampaignDifficulty = 0
CursorCaptureEnabledInFullscreenGame = yes
CursorCaptureEnabledInFullscreenMenu = yes
CursorCaptureEnabledInWindowedGame = yes
CursorCaptureEnabledInWindowedMenu = yes
DrawScrollAnchor = no
DynamicLOD = yes
ExtraAnimations = yes
FirewallBehavior = 1
FirewallNeedToRefresh = FALSE
FirewallPortAllocationDelta = 0
GameSpyIPAddress = 192.168.1.122
GameTimeFontSize = 8
Gamma = 50
HeatEffects = no
IPAddress = 192.168.1.122
IdealStaticGameLOD = High
LanguageFilter = false
MaxParticleCount = 2500
MoneyTransactionVolume = 0
MoveScrollAnchor = no
MusicVolume = 0
NetworkLatencyFontSize = 8
PlayerInfoListFontSize = 8
PlayerObserverEnabled = yes
RenderFpsFontSize = 8
Resolution = 3840 2160
ResolutionFontAdjustment = -100
Retaliation = yes
SFX3DVolume = 79
SFXVolume = 71
ScreenEdgeScrollEnabledInFullscreenApp = yes
ScreenEdgeScrollEnabledInWindowedApp = no
ScrollFactor = 50
SendDelay = no
ShowMoneyPerMinute = no
ShowSoftWaterEdge = yes
ShowTrees = yes
StaticGameLOD = Custom
SystemTimeFontSize = 8
TextureReduction = 0
UseAlternateMouse = no
UseCloudMap = no
UseDoubleClickAttackMove = no
UseLightMap = yes
UseShadowDecals = yes
UseShadowVolumes = no
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

You can also run the Generals Online directly in the same directory:
```
WIWINEPREFIX=~/Games/<your-command-conquer-generals-zero-hour-install-folder>/ wine GeneralsOnlineZH.exe
```

### Problems
At the moment the game exits/crashes as soon as you go to Online and select a Quick Match or select to join a Custom Match


