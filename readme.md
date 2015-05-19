# youtube-playlister

Use this mapping to call it from within ranger, passing along the filename under the cursor:

_rc.conf_

    # run youtube-playlister
    map C shell ./dl %s

The passed along filename will be cut off at the first space and used as starting point for the download. This makes it necessary to use a youtube-dl naming format that starts with %(playlist_index)s.

The variables in `set_variables_for_active_lp()` define which playlist to download and how many files to keep. The `dl` file must be copied to the target folder.
