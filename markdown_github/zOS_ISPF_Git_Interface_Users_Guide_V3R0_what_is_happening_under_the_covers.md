# What is Happening Under the Covers?

When ZIGI opens a repository, the first action is to check the remote server for updates. If there are updates, then the user is informed that the current branch is behind and needs updating \(pull\). ZIGI also checks all the z/OS datasets and the OMVS filesystem for updates, marking the z/OS datasets if there are modifications in play that need to be added to the index, committed, and pushed. If the dataset is a sequential dataset, it is always copied to an OMVS file so that Git can detect changes. For a partitioned dataset, if the member is new then it is copied to the OMVS directory that maps to the PDS. If a file extension has been defined for the PDS, then the member is copied using the file extension – the extension is defined when the dataset is added to ZIGI and stored in the .zigi/dsn file.

This picture provides an example of a ZIGI OMVS filesystem layout.

![](media/img(79).png)

When a partitioned dataset is updated, the ISPF statistics for all members are captured and an OMVS file is updated to accurately reflect the current statistics. This file is then used to compare the members to identify if there are new, or changed, members and then flag them as such. The file is also used during a replace, clone, or pull operation to reset the ISPF statistics as Git has zero awareness of them.

As datasets are added to ZIGI, an OMVS file is updated with the DCB information for that dataset. This file is then used during a replace, clone, or pull operation to correctly allocate the z/OS datasets. The space for those datasets is dynamically determined based on the OMVS filesystem usage and are allocated as PDSE version 2 libraries with a zero MAXGEN.

**Parent topic:**[zOS\_ISPF\_Git\_Interface\_Users\_Guide\_V3R0\_d5e1.html](zOS_ISPF_Git_Interface_Users_Guide_V3R0_d5e1.html)

