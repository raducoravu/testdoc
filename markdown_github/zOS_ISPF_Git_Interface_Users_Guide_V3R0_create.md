# Create

The Create command creates a new local repository that can then later be added to a remote repository.

![](media/img(15).png)

In the above example, a test repository is created in the user's test directory.

Using a ? in the Local Directory field brings up a file directory list from which a directory may be selected or created \(mkdir\) and then selected.

![](media/img(16).png)

The default Push on Commit option, if set to Y, is the default on the Commit panel to push after each commit.

A Read Only repository is one in which the z/OS datasets will never be updated by ZIGI and are intended to track changes to z/OS datasets. All changes are tracked by ZIGI, and thus Git, with all ZIGI features that could update or delete z/OS datasets blocked. These repositories can be pushed to a Git server and then cloned, however clone requires a dataset prefix which should prevent a clone from replacing any existing z/OS datasets.

The Default Userid is set if there is a requirement to change the ISPF statistics userid for each PDS member before a commit.

After the Create process completes, the **Add Datasets** panel displays to facilitate populating the repository with z/OS datasets:

![](media/img(17).png)

This can also be achieved using the ADDDSN command to add existing z/OS datasets to the repository. See the [ADDDSN](#_AddDsn) command, which is not to be confused with the Add row selection, for more information.

**Parent topic:**[The ZIGI Local Repositories Panel](zOS_ISPF_Git_Interface_Users_Guide_V3R0_the_zigi_local_repositories_panel.html)

