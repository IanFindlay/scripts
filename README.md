# Scripts

## A collection of shell scripts I use most of which I have written.

### dwm\_restart
Taken from the [Arch Wiki](https://wiki.archlinux.org/index.php/Dwm#Restart\_dwm). Allows dwm to be restarted without logging out or closing application. Useful when testing a new script or alteration to dwm but something I don't really use.

### dwm\_status\_bar
My bespoke dwm status bar with the following parts:

cmus - Displays Song, Artist, Album, Track Time and has an icon if Shuffle is on. Status updates ~every second when cmus is running, 20 seconds otherwise.

Mullvad VPN - Display a padlock icon when I am connected through Mullvad VPN.

Transmission-cli - Categorises torrents into Downloading, Uploading and Seeded (Ratio >= 1.0) and displays the number of torrents of each type and the accumulated speed of the Downloading and Uploading ones.

Volume - If speaker volume is less than 100% the volume is displayed with a different icon for when it is muted and when my headphones are plugged in.

Date - Displays the current date and time in the following format "Day Date Month HH:MM"

### update\_current\_track, lyrics and show\_lyrics
My three-part solution to being able to have the lyrics of the current song displayed and auto-updating. Uses cmus's status\_display\_program command to write the current track to a file (update\_current\_track) that is then monitored by [entr](https://github.com/clibs/entr) (lyrics) and then show\_lyrics displays the lyrics by reading a local file. Lyrics can be Edited, marked as Instrumental or Searched for at Genius using arguments to show\_lyrics.

### media\_control
Allows me to map my media controls to both cmus (which takes priority) and mpv (which uses xdotool).

### podentr, poddown
Based on [Luke Smith's scripts](https://github.com/LukeSmithxyz) - Improves upon Newsboats podcast downloading by monitoring the queue file (podentr) and downloading podcasts automatically without having to open podboat (poddown).

### remseeded
Uses transmission-remote to remove any torrents that have seeded to or beyond a 1.0 ratio. If there are no torrents, or all torrents were seeded to 1.0 and have therefore been removed, it kills the transmission-daemon.

### setbg
Another Luke Smith inspired scripts, simply uses xwallpaper to set the desktop background either to an already set file, the file supplied as an argument or a random file in a directory passed as an argument.

### torrent\_add
Adds a magnet link via transmission-remote starting transmission-daemon if required.

### torrent\_done
Sends a notification that a torrent has finished downloading through notify-send.

### viddown
Uses youtube-dl to download videos from a url with a notification for both when the file is enqueued and completed.

### volume\_change
Detects if my headphones or speakers are currently in use and alters the volume of the appropriate device. Also kills and restarts dwm\_status\_bar so the volume displayed is up-to-date.
