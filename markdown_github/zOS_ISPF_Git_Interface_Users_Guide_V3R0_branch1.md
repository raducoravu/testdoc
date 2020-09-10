# Branch

Creates and checks out a new branch starting from the commit at which the <stash\> was originally created, applies the changes recorded in the stash to the new working tree and index. If that succeeds, it then drops the stash.

This is useful if the branch on which you ran git stash save has changed enough that git stash apply fails due to conflicts. Since the stash entry is applied on top of the commit that was HEAD at the time git stash was run, it restores the originally stashed state with no conflicts.

**Parent topic:**[The ZIGI Current Repository Panel](zOS_ISPF_Git_Interface_Users_Guide_V3R0_the_zigi_current_repository_panel.html)

