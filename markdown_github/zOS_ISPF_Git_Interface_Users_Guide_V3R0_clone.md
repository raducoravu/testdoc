# Clone

Clone prompts to make a copy of a repository that resides on a remote server on your local OMVS filesystem and into a set of z/OS datasets based on a high-level-qualifier that you provide:

![](media/img(12).png)

In the above example, the remote repository is the ZIGI repository on GitHub. We have selected to enter the local OMVS directory manually, and the HLQ \(prefix\) for the z/OS datasets is specified. If a ? is entered into the Local Directory field, then a dialog is displayed to walk down the OMVS directories to find or make \(MKDIR\) the directory where the cloned repository is placed.

All but the Category, Optional branch name and Repository Name are required fields.

The Repository Name will default, if blank, to the Git name of the repository, otherwise the name here will be used for the local OMVS directory name for the clone operation.

The Category is helpful as a sort option on the Local Repository table display.

The default Push on Commit option, if set to Y, is the default on the Commit panel to push after each commit.

The Default Userid is set if there is a requirement to change the ISPF statistics userid for each PDS member before a commit.

After the cloning is complete, the z/OS datasets in the repository are displayed. This is also the panel that is displayed when the repository is Selected from the Primary panel.

During the clone process, if any existing z/OS datasets are about to be replaced by the clone operation a display will be presented asking for permission, with an option to change the dataset prefix for the clone datasets.

NOTE: ZIGI creates PDSE Version 2 libraries for all partitioned datasets with a default MAXGEN of 0 \(see the [Config](#_Config) command to change the default number of generation\).

![](media/img(13).png)

**Parent topic:**[The ZIGI Local Repositories Panel](zOS_ISPF_Git_Interface_Users_Guide_V3R0_the_zigi_local_repositories_panel.html)

