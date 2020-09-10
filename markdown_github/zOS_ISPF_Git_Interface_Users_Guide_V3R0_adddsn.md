# AddDsn

AddDsn makes it easy to add additional z/OS datasets to the local repository.

![](media/img(32).png)

In the above example, four datasets were already in the local repository and others are available to add.

If the repository is new, and there are no z/OS datasets included, then the Fixed Dataset Prefix and Ignore 1st n qualifiers are blank and must be filled in before the list of z/OS datasets may be presented. The qualifiers to ignore must be at least 1.

The Fixed Dataset Prefix field is the high-level-qualifier \(HLQ\) for the datasets to be presented, from which one, or more, may be selected to add to the repository. Be aware that adding a binary dataset using the A, or S, option adds the dataset as text data and not binary. If the dataset contains binary data, then add it using the AB \(add binary\) option.

If the dataset is a load library \(RECFM=U\), then it will be added as binary and as an executable load module regardless of the selection \(S, A, AB\). If there are aliases associated with any load module then those are retained as well in the copy operation from z/OS to OMVS and restored in the OMVS to z/OS copy.

The Ignore 1st n qualifiers in the prefix field instructs ZIGI to ignore those qualifiers when creating the OMVS file, or directory, for the dataset. Thus GITUSER.ZIGI.ZIGI.README is created in the OMVS filesystem as ZIGI.README. Then when someone else clones this repository the file is uploaded using the HLQ that they provide results in a z/OS dataset of hlq.ZIGI.README. Make sure that the ‘ignore count’ does not exceed the number of qualifiers of the dataset you want to add.

To clarify:

Local z/OS Dataset name: **HLQ.MLQ.TOOL.JCL**

Set ignore qualifier to 2 and the file added to the local repository is **TOOL.JCL**

When someone clones with an HLQ of HENRI.REPOS.CLONES, the z/OS Dataset Name is **HENRI.REPOS.CLONES.TOOL.JCL**

When adding a partitioned dataset, the user is prompted to enter an optional file extension to be used when copying the PDS members to the OMVS filesystem. This enables the use of workstation clients to clone and update a repository by using the file extensions to easily identify the language type within the workstation editors \(e.g. source.c instead of SOURCE\). If the optional extension is not provided, then the member names continue to be copied in uppercase to the OMVS filesystem without any file extensions.

![](media/img(33).png)

There is one restriction that only one file extension is allowed per PDS. This restriction is in place to prevent member name collisions from two files with the same file name but different file extensions \(e.g. source.c and source.jcl\).

This prompt may be disabled for the current set of add’s by entering a Y to disable.

NOTE: This prompt may be bypassed by setting the Bypass option to Y \(yes\) on the **Config** settings panel from the **Local Repository** panel.

**Parent topic:**[The ZIGI Current Repository Panel](zOS_ISPF_Git_Interface_Users_Guide_V3R0_the_zigi_current_repository_panel.md)

