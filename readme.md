# mvscomplete layout for AttractMode front end

by Keil Miller Jr [Keil Miller Jr](http://keilmillerjr.com)

![Image of layout](layout.gif)

## DESCRIPTION:

*mvscomplete* is a layout for the [AttractMode](http://attractmode.org) front end. It was designed because I was seeking a better option than the 161-in-1 multicart for the neo geo. The 161-in-1 multicart has an awful menu, missing games, and a bunch of hacks.

This layout is intended to be displayed at a minimum of VGA resolution (640x480) and will scale gracefully to any higher resolutions, including widescreen resolutions.

## Requirements:

* AttractMode compatible device with AttractMode 2.3.0 or greater installed
* Mame/GroovyMame installed with corresponding neogeo roms and bios (to run neo geo games)

## Paths

You may need to change file paths as necessary if your differs.

## Install Files

1. Copy layout files to ```~/.attract/layouts/mvscomplete/```
2. The [Helpers module](https://github.com/keilmillerjr/helpers-module) is **v1.0.1 REQUIRED** for you to install. The layout will not work correctly without it.
3. The [Shuffle module](https://github.com/keilmillerjr/shuffle-module) is **v2.0.0 REQUIRED** for you to install. The layout will not work correctly without it.

## Optional Files

1. The [Shader module](https://github.com/keilmillerjr/shader-module) is **v1.0.0 RECOMMENDED**. Shader module is required if you intend to use crt shaders within the layout.
2. The [Leap plugin](https://github.com/keilmillerjr/leap-plugin) is **OPTIONAL**. Leap plugin helps to leap over empty filters. Whacky things happen if you have a favorites filter and no roms selected as a favorite!
3. The [FadeToGame plugin](https://github.com/keilmillerjr/fadetogame-plugin) is **OPTIONAL**. FadeToGame will fade the screen when transitioning to and from a game. Be sure to set "To Game Run Time" to at least *1620 milliseconds* if using Navigation Audio in mvscomplete.
4. The [Randtro intro](https://github.com/keilmillerjr/randtro-intro) is **OPTIONAL**. Select specific or random videos to use as an intro.

## Config

* Edit the following files to somewhat match below, or you may use the config menu (tab) inside AttractMode to enter the values. Do not forget to generate the rom index and history index (if being used) from the config menu.

File: ```$HOME/Apps/AttractModeFE/attract.cfg```

```
# Generated by Attract-Mode v2.5.1
#
display	Neo-Geo MVS
	layout               mvscomplete
	romlist              mame
	in_cycle             yes
	in_menu              yes
	global_filter        
		sort_by              Title
		rule                 Tags contains neogeo
		rule                 Category not_contains Majong
		rule                 Category not_contains Quiz
		rule                 Category not_contains Tabletop
	filter               All
	filter               Driving
		rule                 Category contains Driving
	filter               Fighter
		rule                 Category contains Fighter
	filter               Favorites
		rule                 Favourite equals 1
	filter               Maze
		rule                 Category contains Maze
	filter               Platform
		rule                 Category contains Platform
	filter               Puzzle
		rule                 Category contains Puzzle
	filter               Shooter
		rule                 Category contains Shooter
	filter               Sports
		rule                 Category contains Sports
	filter               Year
		sort_by              Year

sound
	sound_volume         100
	ambient_volume       100
	movie_volume         100

input_map
	custom1              R
	custom2              F
	screenshot           F12
	configure            Tab
	add_favourite        LAlt
	back                 Escape
	up                   Up
	down                 Down
	select               Return
	select               LControl
	prev_game            Left
	next_game            Right
	right                Joy0 Right
	left                 Joy0 Left
	next_display         Num1
	next_filter          LShift
	intro                Num2
	default             back	exit
	default             up	prev_game
	default             down	next_game
	default             left	prev_display
	default             right	next_display

general
	language             en
	exit_command         exit_command
	exit_message         Turn off arcade
	default_font         Arial
	font_path            /Library/Fonts/;$HOME/Library/Fonts/
	screen_saver_timeout 600
	displays_menu_exit   yes
	hide_brackets        no
	startup_mode         default
	confirm_favourites   no
	confirm_exit         yes
	mouse_threshold      10
	joystick_threshold   75
	window_mode          default
	filter_wrap_mode     default
	track_usage          yes
	multiple_monitors    no
	smooth_images        yes
	selection_max_step   128
	selection_speed_ms   40
	move_mouse_on_launch no
	scrape_snaps         yes
	scrape_marquees      yes
	scrape_flyers        yes
	scrape_wheels        yes
	scrape_fanart        no
	scrape_videos        no
	scrape_overview      yes
	video_decoder        video_decoder
	menu_prompt          Displays Menu
	menu_layout          menu_layout

layout_config	mvscomplete
	param                artworkShade 40
	param                audio
	param                bloom No
	param                crtShader Crt Lottes
	param                favoritesColor 235, 45, 53
	param                gameTitle Yes
	param                general
	param                marqueeOpacity 75
	param                miniArt Cabinet
	param                navigationAudio On
	param                shaders
	param                videoAudio On

intro_config
	param                bloom Yes
	param                crtShader Crt Lottes
	param                customVideo
	param                defaultVideo random
	param                general
	param                intro On
	param                shaders

plugin	Sequencer
	enabled              yes
	param                delayTime 10

plugin	Leap
	enabled              yes
	param                exception All

plugin	FadeToGame
	enabled              yes
	param                fromGameRunTime 500
	param                toGameRunTime 1620

```

File: ```$HOME/Apps/AttractModeFE/emulators/mame.cfg```

```
# Generated by Attract-Mode v2.5.1
#
executable           /Applications/mame0200b_macOS/mame64
args                 [name]
rompath              /Applications/mame0200b_macOS/roms
romext               .zip;.7z
system               Arcade
info_source          listxml
import_extras        /Applications/mame0200b_macOS/catver.ini;/Applications/mame0200b_macOS/mame0200.xml
nb_mode_wait         1
exit_hotkey          Escape
pause_hotkey
artwork    flyer
artwork    marquee
artwork    snap            /Applications/mame0200b_macOS/videosnaps/;/Applications/mame0200b_macOS/snap/
artwork    wheel           /Applications/mame0200b_macOS/wheels/

```

## Artwork

Artwork for front end in general can be obtained from the following:

* [AntoPISA's progetto-SNAPS MAME Snapshots - Snap](http://www.progettosnaps.net/snapshots/) for snaps
* [Emumovies](http://emumovies.com) for videos
* [HypserSpin](http://www.hyperspin-fe.com) for wheel artworks
* [PleasureDome](https://www.pleasuredome.org.uk) for continuously updated torrent packages containing full sets continuously updated.

## Credit

Artwork for this layout were obtained from the following locations:

* [star.png](https://www.tenstickers.pt/autocolantes-decorativos/vinil-decorativo-estrela-militar-9818)

Audio for this layout were obtained from the following locations:

* [click.wav](https://freesound.org/people/airblock/sounds/407720/) by [airblock](https://freesound.org/people/airblock/)
* [select.mp3](https://freesound.org/people/killkhan/sounds/150222/) by [killian](https://freesound.org/people/killkhan/)
