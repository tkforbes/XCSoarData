WARNING - not ready for general use.

## What is this?

This repository contains a configuration for XCSoar. It is a convenient restore point or starting point for the configuration of a Kobo-based device already running XCSoar. This configuration will not install XCSoar. You have to do that first. The proceedure is not described here.

## xcsoar-version

The following version of XCSoar is loaded on the Kobo Mini. The configuration may or may-not work with other hardware and XCSoar versions.

### As displayed on XCSoar Menu -> Info 3/3 -> Credits
```
- 6.8.16-Kobo
- Jul 26 2020
```

## Terms

The following terms are used to describe the Infoboxes used by this configuration. The terms themselves come from XCSoar's display of the infobox settings on the Config->System->Look->Infobox Sets page.

- **Alt** : Altitude
- **Altn** : Alternate (landing site)
- **Cruise / Circling / Final glide** Detected flight modes that control the auto-display of a screen and its infoboxes.
- **GR** : Glide ratio
- **MC** : MacCready value
- **TC** : Thermal current
- **TL** : Thermal last
- **WP** : Waypoint

## Screens and Infoboxes

The configuration is set for Portrait mode with a set of 8 infoboxes at the base of the page. Moving maps are displayed in North Up orientation. The glider's position on the map drifts back such that the view ahead is given more room than the territory behind (aka Map Shift). Flarm traffic can be displayed depending on equipment and correct configuration. The moving map trail identifies areas of lift (thick lines) and sink (thin). An arrowhead displays the calculated wind. To ensure the map is clutter-free, terrain and topographic information is not displayed. Airspace is displayed but warnings are disabled because it is relatively simple to remain aware of position and to alert Ottawa Terminal as required. A safety arrival height is set at 900ft. The alternate landing site is chosen by the *simple* option. Safety MC is set at 0.7 m/s. Auto MacCready mode is *Both*. Speed To Fly is for zero lift/sink ie *Block* mode. 

The computer displays one of the the following three pages depending on detected flight mode. The moving map is displayed above the infobox set.

| Circling ||||
|---|---|---|---|
TC 30s | TC Gain | WP Dist| Alt |
TL Avg | TC Avg | WP AltD | Altn 1 GR|

| Cruise ||||
|---|---|---|---|
|WP GR | MC | WP Dist| Alt |
|TL Avg | GR Inst | WP AltD | Altn 1 GR|


| Final Glide ||||
|---|---|---|---|
| WP GR | MC | WP Dist| Alt |
| TL Avg | GR Inst  |WP AltD | Altn 1 GR|

A separate file in this repository named *infoboxes--full-list.md* gives a full list of infobox choices that you 
can substitute in any of the above groups.

## Method

### Warning

You will replace the current configuration of your flight computer. Any important settings will be lost. 
To recover them, you must have a backup of the *XCSoarData* directory (and its children).

### On Linux (Ubuntu) and using git

#### Make the connection between the Kobo and the computer.

On Linux, the Kobo needs to be connected to the computer and its filesystem mounted. To do this...

1. Clone the repository and change to the project directory i.e. *$ git clone https://github.com/tkforbes/xcsoar-setup.git*
1. Switch to the *kars* branch i.e. *$ git checkout kars*
1. Connect a USB cable between the Kobo and Linux desktop. **Exit XCSoar, if running.**
1. From the XCSoar main page, choose *Nickel*. Wait a while. A screen displaying *Welcome to Kobo* appears.
1. Choose *Computer Setup*. This creates a mount point at /media/your-name/KOBOeReader. *Connected and charging* appears on the screen.

#### Put the configuration on your Flight Computer

In your terminal, you should be in the correct directory, which is something like this...

```
tf@goliath:~/git/xcsoar-setup$ pwd
/home/tf/git/xcsoar-setup
```

Sync the configuration files to the flight computer with this command...

```
rsync --exclude-from=rsync-exclude.list -av ./ /media/tf/KOBOeReader/XCSoarData/
```

then

1. Eject the Kobo (same as unmount the Kobo).
1. Power-off the Kobo. *Powered off* appears. Wait a moment.
1. Power-on the Kobo. 
1. Select Fly from the XCSoar main screen.
1. Select M(enu)->Config 1/3->System->Setup->Logger and change Pilot Name.
1. Select M(enu)->Config 1/3->System->Plane and chose your aircraft from the list and press Activate.


## Backup your XCSoar

## Install these configuration settings
