# webonairsmpctricks
I bound some of my media player keys to these brief scripts.  They involve mpd, mpc and dmenu.

From my i3config:
```
#Media keys
bindsym XF86AudioPlay exec mpc toggle
bindsym XF86AudioNext exec mpc next
bindsym XF86AudioPrev exec mpc prev
bindsym Shift+XF86AudioPrev exec mpc clear
bindsym XF86AudioStop exec "mpctricks cueSong"
bindsym Shift+XF86AudioStop exec "mpctricks cueAlbum"
bindsym Ctrl+XF86AudioStop exec "mpctricks cuePlaylist"
bindsym Ctrl+XF86AudioPlay exec "mpctricks add2playlist"
bindsym Shift+XF86AudioPlay exec "mpctricks reroll"
```
- The `cue` functions let you filter through your mpd library using dmenu.  It doesn't stop playback to cue a song; albums play in track order; playlists are shuffled.
- `add2playlist` appends the playing track to the m3u file of the playlist.
- `reroll` clears the playlist and shuffles the whole library.
- `bg` changes the desktop background to a crop of the album cover.  It sucks because it assumes you're using one 1366x768 monitor, plus it only checks for "image.jpg" within the song's directory...  To automate it, I added this to my ncmpcpp config: `execute_on_song_change = "mpctricks bg"`
