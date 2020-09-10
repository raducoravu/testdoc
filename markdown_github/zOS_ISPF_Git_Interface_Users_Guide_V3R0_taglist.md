# TagList

TagList displays a selection table of all the Tags.

![](media/img(62).png)

The table may be filtered using the Only command \(e.g. only x\) and Refresh recreates the table with all entries.

Row selection of S displays the tag details while selection of C creates a new branch based on the tag level of the repository. This not only changes the OMVS filesystem files to match the tag level file, it also replaces all z/OS datasets to the tag level.

Selection X will extract all the changed elements from all the selected tags into a non-Git managed set of z/OS datasets and OMVS directory. This can be used for packaging to distribute only the updated elements \(e.g. PTF\).

A row selection option of / brings up this pop-up:

![](media/img(63).png)

A confirmation pop-up asks for the name of a new branch for the tag level code:

![](media/img(64).png)

**Parent topic:**[The ZIGI Current Repository Panel](zOS_ISPF_Git_Interface_Users_Guide_V3R0_the_zigi_current_repository_panel.html)

