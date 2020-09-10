# GitLog

This command displays the git log information.

When requested, a pop-up is presented to request the amount of log information to report:

![](media/img(46).png)

NOTE: The date format is yyyy/mm/dd, which is translated to yyyy-mm-dd and is required by Git. The reason for this is that we are using the ISPF Panel verify for standard dates to verify the date.

The Filter is a string that is used by grep to filter commits to that string. No blanks allowed.

The values entered are remembered in the user's ISPF Profile for repeated use.

The git log command is executed using the --cc and -m options along with the appropriate options for the above values. After which ISPF view \(or browse – no special colors with browse\) is invoked on the results:

![](media/img(47).png)

**Parent topic:**[The ZIGI Current Repository Panel](zOS_ISPF_Git_Interface_Users_Guide_V3R0_the_zigi_current_repository_panel.md)

