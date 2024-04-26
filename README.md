# Preface
So theses are sanitized versions of the scripts I use for i3.
I use some fontawesome symbols, so you may want that or can just swap them out
# Scripts
## currPlay
Uses playerctl to get a formatted string of:
    `<play status> <artist> - <song> [<position>/<total>]`
It should work for most programs that play audio including rhythmbox, spotify, and firefox. 

Controls:
- Left click: `play-pause`
- Middle click: `stop`
- Right click: none
- Scroll up: `next song`
- Scroll down: `previous song`

There is an echo statement that will color the string to the album art, but i3blocks cannot read the ansi codes...if I even get the right colors.
This might also not work if the files are not local.
## cycleSink
Originally this script was made to switch the audio sinks between sources, so mind the format. It utilizes pacmd to monitor and switch the current sink. The i3block should be like:
    `<source symbol>: <sink volume>%`

Use `pacmd list-sinks` or some equivalent to get the name of the sink to use. It likely has a format of `alsa_output.`... or `bluez_sink.<mac address>`...

If using a bluetooth device as a source, I suggest disconnecting the bluetooth connection for every other source.

Controls:
- Left click: `toggle mute`
- Middle click: `open rhythmbox` 
- Right click: none
- Scroll up: `increase sink volume by 5%`
- Scroll down: `decrease sink volume by 5%`
## colorPicker
This one just gets a hex value of the album art that is currently on playerctl. Its not actually used unless you want to figure out how to use it with currPlay. It works by reducing the image down and getting the most common color in hex