# Set

Set is used to define default actions for the user:

![](media/img(55).png)

The Name of the Repository is the name of the OMVS directory where the repository resides and if changed will only result in the name of the repository in the Local Repositories table. The directory will not be changed.

The Category is an arbitrary description for the repository that allows the user to categorize, or group, repositories.

The Prefix is used to define the z/OS dataset HLQ that was used when the repository was created or cloned. The Prefix may be changed, and all z/OS datasets are renamed, and depending upon the qualifiers to ignore \(see the INFO display\) it is possible the OMVS files and directories may be renamed as well. To change the Prefix requires that the new prefix have the same number of qualifiers as the original prefix. If OMVS files and/or directories are changed, then git is also updated to be aware of the rename.

The Commit panel has an option to Push after the Commit. This setting provides a default, which the user may override on the Commit panel anytime.

The Userid is what all PDS members ISPF Stats are set to when they are processed by Commit. Only those members have their ISPF Stats updated to the specified userid.

NOTE: Do not use 8-character userids unless your system has enabled their use.

The option to Disable File Extension prompting can be enabled or disabled here.

If the repository is to be distributed to others who may not have ZIGI installed then use the Prime Repository with the zginstall.rex option to place a zginstall.readme and the zginstall.rex into the repository. See the section on [zginstall](#_Appendix_B:_Using) below.

**Parent topic:**[The ZIGI Current Repository Panel](zOS_ISPF_Git_Interface_Users_Guide_V3R0_the_zigi_current_repository_panel.html)

