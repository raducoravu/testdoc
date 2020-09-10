# Flow

To assist users in their workflow, ZIGI helps the user via the ZIGIflow commands.

The FLOW command brings up this pop-up menu:

![](media/img(40).png)

The **Handy Functions** action bar menu is similar:

![](media/img(41).png)

A new ZIGI flow can be started at any time if the workspace is clean. In other words, there can be no local changes that are not committed to the current branch.

![](media/img(42).png)

When starting a new ZIGI flow, ZIGI prompts the user for a flow name. Internally this is used as a branch name, so spaces are not allowed.

Upon starting a flow, ZIGI checks out the master branch, create a new branch called zigiflow-<yourFlowName\>, and also creates a <yourFlowName\> branch. Both of these branches are identical to master.

Then the user can make changes, commit, and once done, finish the flow. Upon finishing the flow, all the commits from the zigiflow branch are ‘squashed’ into the final branch at which point this can be merged into the master or pushed out to a remote repository so a pull request might be issued.

Due to the way zigiflow manages the internal branching, it’s easy for the user to \(once the workspace for their current work is clean, e.g. work-in-progress is committed to the ‘flowbranch’\) they can easily start *another* zigiflow \(always based on master\) to perform some efixing. Once that flow is done, the resulting branch can be merged to master \(or pushed for a pull request\) *and* also be merged into the ‘other workflow’.

Switching between workflows is done via option 3 and again, this can only be done in a clean workspace.

![](media/img(43).png)

**Parent topic:**[The ZIGI Current Repository Panel](zOS_ISPF_Git_Interface_Users_Guide_V3R0_the_zigi_current_repository_panel.md)

