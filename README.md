WARNING - not ready for general use.

# xcsoar-setup

This is the collection of default files and settings that I use for soaring from the Kars airfield.

## xcsoar-version

The following version of XCSoar is loaded on my Kobo Mini

```
From Menu -> Info 3/3 -> Credits.
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
