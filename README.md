# TiVo To Go Plex Channel Plugin

This Plex plugin uses the TiVo To Go API to watch a stream off, or download a recorded program from, a TiVo DVR. It requires a Series 2 or newer TiVo with a network connection. The Plex Media Server (PMS) should have a high speed connection between itself and the TiVo.

_Q:_ What would I use this channel for?

_A:_ You can browse to a show on your TiVo through Plex and watch (stream) it without needing to first download it to your PMS.

_Q:_ Can I download something from the TiVo to the Plex Media Server using this channel?

_A:_ Yes! If you enable the download option and specify a folder name, the plugin will display an extra menu item to download the content to your PMS.

   _NOTE:_ You should create a library on your PMS which points to the same directory that you are downloading the files into. If you name the Plex library "TiVo To Go" it will automatically get refreshed when downloads are initiated _and_ when they complete. If
   you want to name the Plex library something different (or include it in multiple libraries) simply add the name(s) in the plugin preferences (see the Steps section below).

- - -
## Installation

### Requirements

- Linux, OSX or Windows Plex Server (no ARM processor NAS support)
- on Linux, OSX or X86 NAS, [curl](https://curl.haxx.se/) must be installed

### Steps

1.  Install curl if you don't already have it
2.  Copy the TiVoToGo.bundle to your plugin directory:
    * Mac: ~/Library/Application Support/Plex Media Server/Plug-ins
    * Windows: C:\Users\\_&lt;username&gt;_\AppData\Local\Plex Media Server\Plug-ins
    * Linux: /var/lib/plexmediaserver/Library/Application Support/Plex Media Server/Plug-ins
3.  Make sure to update the plugins settings:
    * Enter your Media Access Key (MAK) from the TiVo
    * Enter an IP address for the TiVo if the Plex Server is on a different subnet (then exit the channel and start it again)
    * If you want enable the offline downloads check the "Enable To Go downloads" box and fill in a directory that is writable by the plex user
    * Enter the name of the Plex library to automatically refresh once a download has started. If left blank, this will default to "TiVo To Go." You can enter multiple library names, separated by commas if you want. This lets you add your download directory to multiple libraries using different metadata agents (i.e., for TV Shows and Movies)
    * If you want the plugin to [properly name](https://support.plex.tv/articles/200220687-naming-series-season-based-tv-shows/) your downloaded file (for Plex agent metadata lookups), enter your TiVo Online username and password in the appropriate fields. 

- - -
## To Do

- use the urllib instead of curl
- stop using /tmp/cookies.txt
- use dynamic sockets and a fixed URL for the live stream video
- if the community support for the MPEG-TS improves, add MPEG-TS support, for now it only works with MPEG-PS
- validate TiVo credentials when saving preferences (in the validatePrefs placeholder)
- set thumbnails for folders, episodes, download action, etc.

- - -
## Contact

Jeremy C. Radwan

- https://github.com/jradwan
- http://www.windracer.net/blog

- - -
## References

rpcSearch125.py from [MetaGenerator 3](https://pytivo.sourceforge.io/forum/metagenerator-version-3-t1786.html)

https://github.com/tivoguy/TiVoToGo.bundle

https://github.com/sander1/TiVoToGo.bundle
