WARNING - not ready for general use.

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

## Screens and Infoboxes.

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


# xcsoar-setup

This is the collection of default files and settings that I use for soaring from the Kars airfield.

## xcsoar-version

The following version of XCSoar is loaded on my Kobo Mini

### From Menu -> Info 3/3 -> Credits.
```
- 6.8.16-Kobo
- Jul 26 2020
```
## Method

On Linux, the Kobo needs to be connected to the computer and its filesystem mounted. To do this...

Connect a USB cable between the Kobo and Linux desktop. Exit XCSoar, if running.

Choose "Nickel", Computer Setup. This creates a mount point at /media/tf/KOBOeReader

Sync the files from the flight computer to the repo and check for any differences.

```
tf@goliath:~/git/xcsoar-setup$ pwd
/home/tf/git/xcsoar-setup
```

## Get the configuration from Kobo / XCSoar
```
rsync --exclude-from=rsync-exclude.list -av /media/tf/KOBOeReader/XCSoarData/  ./
```

## Put the configuration back to Kobo / XCSoar
```
rsync --exclude-from=rsync-exclude.list -av ./ /media/tf/KOBOeReader/XCSoarData/
```


This is a first-cut. The documentation needs to be improved and the process of installation clarfied. There has to a list of .gitignore files to make it easier to disregard information that may leak to this location from someone's actual fligth computer. A good example of this is log files and crash files.

I will also have to consider what files are of personal interest and which are of general interest. For the repository to have broad appeal, there has to be an acceptance of 'standards' such as the names of waypoints and their official locations. How will I differentiate between waypoints that are valuable from year-to-year and those which have value for short periods, such as the locations of farm strips which tend to come and go, or of good agricultural fields which might serve as a landing option at the start of the season but become unsuitable as the crop grows.
