# Using CBTTape

You can also download ZIGI from [https://www.cbttape.org](https://www.cbttape.org) in file 997. Be sure to check on the [Updates](http://www.cbttape.org/updates.htm) page on the left menu for the latest release, and if you do not see it there, then go to the CBT page on the left menu.

1.  Download FILE 997 to your workstation and unzip.
2.  Binary upload the resulting XMIT file to z/OS using RECFM=FB LRECL=80
3.  From TSO, or ISPF Option 6, issue RECEIVE INDS\(upload-file-name.xmit\)
    1.  Enter a dataset name or take the default
4.  Open the resulting PDS and execute the $INSTALL member, which receives the EXEC and PANELS members into full partitioned datasets.
5.  Edit the PDS member STUB to customize for your site and then copy it into a library in your SYSPROC or SYSEXEC allocations under the name ZIGI.
6.  Start ZIGI from any ISPF Panel by entering TSO %ZIGI.
7.  To use the ZG command, it must be copied from the ZIGI.EXEC library into a library in the standard SYSEXEC, or SYSPROC, allocation.

**Parent topic:**[Installing ZIGI](zOS_ISPF_Git_Interface_Users_Guide_V3R0_installing_zigi.md)

