# Replace

Replace replaces all of the current z/OS datasets in the repository with the data in the local repositories OMVS filesystem, including maintaining the ISPF statistics when those datasets were added to the OMVS filesystem. All refreshed partitioned datasets are allocated as PDSE version 2 libraries with the default MAXGEN. If the refreshed library is a PDS, and more than 25% of the members are being updated, then the PDS is re-allocated as a PDSE Version 2 with the default MAXGEN. If the refreshed library is a PDSE then it is not be reallocated and only the updated members are refreshed.

**Parent topic:**[The ZIGI Current Repository Panel](zOS_ISPF_Git_Interface_Users_Guide_V3R0_the_zigi_current_repository_panel.md)

