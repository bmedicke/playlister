# playlister

Playlister searches for a `.playlister` file in the current directory and uses the first line as the URL for the playlist. It downloads 10 files starting with the number that is passed as an argument.

If there are more than 10 .mp4 files in the current directory it deletes as many files as necessary, starting with the lowest IDs.

## ranger integration

Use this mapping to call it from within ranger, passing along the filename under the cursor:

_rc.conf_

    # run playlister and pass name of file under cursor:
    map P shell playlister %s

The passed along filename will be cut off at the first space and used as starting point for the download. This makes it necessary to use a youtube-dl naming format that starts with %(playlist_index)s.

## installation

Copy playlister to somewhere in your path and make sure it's executable. Add the above mapping to ranger.
