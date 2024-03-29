A collection of some scripts I've gotten from Reddit and modified or created on my own to help managing my UnRAID server.
Mostly tailored for my specific usage, but you're more than welcome to alter and use for your own server.
&nbsp;

#### Backup Scripts
- [general-share-backup-script](/general-share-backup-script)
    - Can be used to create a backup of any of your UnRAID shares or really any folders.  
- [plex-backup-script](/plex-backup-script) 
    - Backup the entirety of `Plug-ins` and `Plug-in Support`, which includes databases, preferences, configuration information (ignores metadata, cache, crash reports, etc.), and backs up `Preferences.xml` to maintain current server preferences and identification.
- [rclone-b2-backup-script](/rclone-b2-backup-script) 
    - A script that runs some rclone sync commands to backup my various backup folders from my external drive to my b2 buckets.  Runs every Sunday morning at 4am.
- [backup-usb](/backup-usb) 
    - Compress and backup the USB boot drive (similar to [general-share-backup](/general-share-backup-script), just with preset source of the boot directory)
&nbsp;

#### General scripts
These scripts, while useful are not for directly backing up.

- [Daily Script](/daily-script) 
    - Runs daily and performs some basic cleanup, like deleting dangling images, checks the IP reported by QbittorrentVPN and my public IP.  It also creates a text for each of my plex libraries and lists out every file that are in each directory so that in case if a major crash and extreme data loss, I will have a list of the files I had before and can start recovering.  It's way easier, less time consuming, and much cheaper than storing terabytes of files offsite.
- [nvidia-patch](/nvidia-patch) 
    - Patches nvidia drivers to support more than the 2 stream limit for consumer cards.  (Fairly sure this has been increased, but this patch fully unlocks it).  Run once on start up.
- [refresh-photoprism](/refresh-photoprism) 
    - Refresh images and clean up any existing images for deleted files in Photoprism.  I run this every night at 11, after my wife and my phones have done their image backup to the server.
&nbsp;

#### Game Backup Scripts
Scripts used to backup various game data.
- [Palworld Backup](/palworld-backup-script) 
    - Very fast script that backs up and compresses important Palworld server saves and config files.  Tested with ich777 palworld container.  Backs up the following directories:
    - Server and player save data - `/mnt/user/appdata/palworld/Pal/Saved/SaveGames/`
    - Server Config data - `/mnt/user/appdata/palworld/Pal/Saved/Config/`