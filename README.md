# rofi-mpc
Fast graphical Rofi-Interface for contolling MPD  
now in the AUR! *aur/rofi-mpc*
## Features
#### Current list of features:
* Volume Control
* Play & Pause
* Prev & Next
* List and Play playlist entries
* Source Selection:
  * Playlist generation for the **~/Music** directory
  * List and Load playlists from mpd's **playlist_directory**
#### Planned features:
* "Copy & Paste" Stream URLs
* Saving Stream URLs as .m3u in mpd's **playlist_directory**
* Switching between local and remote mpd servers for remote control
## Installation
#### Requirements
* **python**
* **mpd**
* **rofi**
#### Recommended Configuration of mpd
Recommended config path:
```
mkdir -p ~/.config/mpd/playlists
```
Recommended **~/.config/mpd/mpd.conf**:
```
db_file				"~/.config/mpd/database"
log_file			"~/.config/mpd/log"
restore_paused			"yes"
music_directory			"~/Music"
playlist_directory		"~/.config/mpd/playlists"
pid_file			"~/.config/mpd/pid"
state_file			"~/.config/mpd/state"
sticker_file			"~/.config/mpd/sticker.sql"
```
Start mpd on boot or at xinit like this:
```
mpd ~/.config/mpd/mpd.conf
```
#### Deployment
```
sudo wget -O /usr/local/bin/rofi-mpc  https://raw.githubusercontent.com/Marco98/rofi-mpc/master/rofi-mpc
sudo chmod +x /usr/local/bin/rofi-mpc
```
Then you just need to set a keybind for rofi-mpc
For example, if you're using i3wm you just need to add this line in you config:
```
bindsym $mod+a exec rofi-mpc
```
#### Adding Streams
If you're using my recommended **mpd.conf** you just need to add it into the playlists-directory like this:
```
echo "http://example.com/stream.mp3" > ~/.config/mpd/playlists/[STREAM-NAME].m3u
```
