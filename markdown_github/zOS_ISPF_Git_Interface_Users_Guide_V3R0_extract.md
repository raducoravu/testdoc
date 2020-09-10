# Extract

Extract provides the user with several options working with the current repository.

The extract selection display is:

![](media/img(36).png)

Use ONLY \(abbreviation O\) followed by a short string to limit the display of items to those that match the string in the commit title.

Use REFRESH \(abbreviation R\) to restore the full display.

Select the individual commit to view it:

![](media/img(37).png)

Or select using R to Rollback to that commit level:

![](media/img(38).png)

This pop-up requires the name of a new branch and that the word ROLLBACK be entered in UPPERCASE to confirm that you want to do it.

Option X is used to extract all the changed elements from all the selected commits into a set of non-Git managed datasets and OMVS directory. This can be used for packaging to distribute changes to others \(e.g. create a PTF\). When multiple commits are selected, all changed elements from all selected commits is collected, then the most recent commit level is checked out to a temporary branch from which the changed elements are copied from.

The extract prompt:

![](media/img(39).png)

Enter a HLQ for the extracted z/OS datasets and an optional OMVS directory \(must not currently exist as it will be created\) into which the changed elements will be copied.

**Parent topic:**[The ZIGI Current Repository Panel](zOS_ISPF_Git_Interface_Users_Guide_V3R0_the_zigi_current_repository_panel.html)

