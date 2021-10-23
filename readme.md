# playlister
Keeps the 10 least recent, unwatched videos of a youtube playlist on your disk. Always have something to watch and avoid cluttering your SSD. 


## how to use it

    mkdir ted && cd ted
    echo "http://www.ted.com/playlists/171/the_most_popular_talks_of_all" > .playlister
    playlister

After watching one or more videos open rangen and press `P` on the first unwatched video. Playlister will make sure you have up to 10 videos and clean up anything more than that.

### passing additional parameters to yt-dlp

Simply put them on the second line:

```sh
https://www.youtube.com/playlist?list=XXXXXX
--cookies cookies.txt --extract-audio --audio-format mp3 --keep-video
```

## how it works
Playlister searches for a `.playlister` file in the current directory and uses the first line as the URL for the playlist to download. The second line is passed along to yt-dlp as optional switches. It fetches 10 files starting with the number that is passed as an argument (or extracted from a filename). If the first argument is no number or is empty it defaults to 1. 

## installation

* install yt-dlp
* make sure playlister is in your path
* optionally add a mapping for ranger

## ranger integration

Use this mapping to call it from within ranger.

_rc.conf_

    # run playlister with the name under the cursor as an argument:
    map P shell playlister %s
