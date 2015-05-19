# playlister
Keep 10 unwatched videos of a playlist on your disk. Always have something to watch and avoid cluttering your SSD. 


## how to use it

Open rangen and press `P` on the video you are currently watching. Playlister makes sure you have 10 videos downloaded and cleans up old videos if you have any more than that.

## how it works
Playlister searches for a `.playlister` file in the current directory and uses the first line as the URL for the playlist to download. It fetches 10 files starting with the number that is passed as an argument (or extracted from a filename). If the first argument is no number or is empty it defaults to 1. 

If there are more than 10 .mp4 files in the current directory it deletes as many files as necessary, starting with the lowest IDs.

## installation

* install youtube-dl
* copy playlister to somewhere in your path
* optionally add a mapping for ranger

## ranger integration

Use this mapping to call it from within ranger.

_rc.conf_

    # run playlister and pass name of file under cursor:
    map P shell playlister %s

_Note in case you decide to change the naming format_: The passed along filename will be cut off at the first space and used as starting point for the download. This makes it necessary to use a youtube-dl naming format that starts with %(playlist_index)s.