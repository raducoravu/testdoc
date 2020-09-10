# Appendix A – Installing Git

|Check|Action|
| |Create an OMVS user account with SuperUser \(su\) capabilities \(for installing Git ‘systemwide’\).|
| |Allocate a good size ZFS \(one that we are using is 500-600 cylinders\).|
| |Get access to PARMLIB member BPXPRMxx or someone who can update it for you to add the appropriate MOUNT statement for the new ZFS.|
| |Download and install the Git package from Rocket Software. Go to [https://www.rocketsoftware.com/product-categories/mainframe/git-for-zos](https://www.rocketsoftware.com/product-categories/mainframe/git-for-zos) to get started. Be sure to download Git, bash, gzip, and perl and bring all those files to one directory in USS.

 -   Per the git README.ZOS, you may also need to download: unzip and vim.

|
| |Go to [https://gist.github.com/wizardofzos/897b243d4cbe9fbc471ec1396fbbe174](https://gist.github.com/wizardofzos/897b243d4cbe9fbc471ec1396fbbe174) and download the installer into the same directory as the things you downloaded from Rocket Software.|
| |Upload the files to a ZFS on z/OS. This ZFS does not have to be the same as the intended ZFS where Git, et.al., is installed. This may be your personal home directory if the filesystem is large enough \(or can grow enough\).|
| |Mount the created ZFS to a mount point. This is the target for Git and related tools.|
| |Get into OMVS.|
| |Go to the directory where the installer was placed and the git packages were uploaded to.|
| |Run the installer script, and when prompted, provide the path to the mounted ZFS that is home to git and tools.|
| |Review the installation.|
| |Find the **environment.sh** file and copy the contents into your **/etc/profile** file.

 **WARNING**: If you installed into a path that is not the production path, then be VERY CAREFUL as you have to edit the environment.sh values before placing into /etc/profile.

 Suggest also adding to the profile **export GIT\_PAGER=more** unless you have installed a ported version of less.

|
| |Exit OMVS and get back into OMVS, and then enter the command **git version** – if it works you have Git.|
| |When happy:

 -   Remove\_dist.sh script to rm the downloaded files
-   The uninstall.sh to:
-   Remove the environment.sh
-   Remove the remove\_dist.sh
-   Remove other installation files

|
| |Now, unmount the Git and tools zfs from the temporary mount point.|
| |Create a new, permanent mount point and mount it.|
| |Update PARMLIB BPXPRMxx with the MOUNT statement so that it is mounted at each IPL:

 **MOUNT FILESYSTEM\(‘OMVS.GIT.ZFS’\)**

 **TYPE\(ZFS\)**

 **MODE\(READ\)**

 **MOUNTPOINT\('/usr/ported'\)**

|

**Parent topic:**[zOS\_ISPF\_Git\_Interface\_Users\_Guide\_V3R0\_d5e1.html](zOS_ISPF_Git_Interface_Users_Guide_V3R0_d5e1.html)

