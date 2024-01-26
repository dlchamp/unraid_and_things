A collection of some scripts I've gotten from Reddit and modified or created on my own to help managing my UnRAID server.
Mostly tailored for my specific usage, but you're more than welcome to alter and use for your own server.

#### Backup Scripts
- [general-share-backup-script](/general-share-backup-script) - Can be used to create a backup of any of your UnRAID shares or really any folders.  
- [plex-backup-script](/plex-backup-script) - Used to backup the only two things that really matter from Plex.  `com.plexapp.plugins.library.db` and `com.plexapp.plugins.library.blobs.db` as these contain all data for watch history, users, libraries, structure, some text metadata, playlists, etc.  Just keeping these two databases has cut my backup size from over 300gb to just over 2 gb since I'm not also backuping up all the generated thumbnails, intro/credits, and posters.
- [rclone-b2-backup-script](/rclone-b2-backup-script) - A script that runs some rclone sync commands to backup my various backup folders from my external drive to my b2 buckets.  Runs every Sunday morning at 4am.
- [backup-usb](/backup-usb) - Compress and backup the USB boot drive (similar to [general-share-backup](/general-share-backup-script), just with preset source of the boot directory)

#### General scripts
These scripts, while useful are not for directly backing up.
- [Daily Script](/Daily%20Script) - Runs daily and performs some basic cleanup, like deleting dangling images, checks the IP reported by QbittorrentVPN and my public IP.  It also creates a text for each of my plex libraries and lists out every file that are in each directory so that in case if a major crash and extreme data loss, I will have a list of the files I had before and can start recovering.  It's way easier, less time consuming, and much cheaper than storing terabytes of files offsite.
- [nvidia-patch](/nvidia-patch) - Patches nvidia drivers to support more than the 2 stream limit for consumer cards.  (Fairly sure this has been increased, but this patch fully unlocks it).  Run once on start up.
- [refresh-photoprism](/refresh-photoprism) - Refresh images and clean up any existing images for deleted files in Photoprism.  I run this every night at 11, after my wife and my phones have done their image backup to the server.