# Pop

Removes a single stashed state from the stash list and applies it on top of the current working tree state, i.e., do the inverse operation of Git stash save. The working directory must match the index.

For simplicity sake, ZIGI validates that the current workspace is clean before performing a stash pop. This is because numerous conflicts could arise that would require manual intervention and the authors were unable to find a reliable methodology to resolve those conflicts programmatically.

**Parent topic:**[The ZIGI Current Repository Panel](zOS_ISPF_Git_Interface_Users_Guide_V3R0_the_zigi_current_repository_panel.md)

