# Getting Started

To start ZIGI the first time:

1.  In ISPF, use option 3.4 and enter the HLQ provided during the installation process or enter DSLIST hlq on the ISPF command line.
2.  Select the EXEC dataset using Browse, Edit, or View.

    Note: ZIGI saves its repository ISPF table in the dataset referenced by ISPTABL, but if that DD is not used then it uses the DD ISPPROF as the location for the table.

3.  Next to the ZIGI member, enter EX to execute it.

    This exec is the main ZIGI code and dynamically allocates the EXEC library using ALTLIB and the PANELS library using LIBDEF.


![](media/img(1).png)

1.  A more permanent option is to edit this sample REXX code, make the necessary customizations, and place it in a library in your SYSEXEC concatenation and invoke from any ISPF panel using the command TSO %ZIGI. This sample can be found in the provided EXEC library under the name SAMPLE.

/\* --------------------- REXX -------------------------------- \*

\| This is a REXX exec that may be copied into a system level, \|

\| group level, or personal SYSEXEC or SYSPROC library for the \|

\| purpose of making it easy to invoke ZIGI. \|

\| \|

\| To use customize the exec and panels variables. \|

\* ----------------------------------------------------------- \*/

arg opt

exec = "**'hlq.exec'**" /\* <=== update \*/

panels = "**'hlq.panels'**" /\* <=== update \*/

Address TSO 'altlib act application\(exec\) dataset\('exec'\)'

Address ISPexec

'libdef ispplib dataset id\('panels'\) stack'

"Select CMD\(%ZIGI" opt"\) Newappl\(ZIGI\) Passlib Scrname\(ZIGI\)"

'libdef ispplib'

Address TSO 'altlib deact application\(exec\)'

The ZIGI Splash panel is presented.

![](media/img(2).png)

1.  Next, the user is prompted for their username and e-mail along with two ZIGI processing defaults:
    1.  The PDSE member generations default value – it is recommended to use 0 unless you have a tool that supports working with member generations.
    2.  The Display Options Pop-up option changes the behavior of point-and-shoot so that on table panels a click above the table displays the commands pop-up and anywhere in the table the line selection pop-up options.
    3.  Set the Bypass File Extension Prompt if you do not plan to use file extensions for the OMVS files.

![](media/img(3).png)

1.  After providing your name and e-mail, if you haven’t created an SSH key pair yet, ZIGI creates this for you and shows you the public part of the keypair that you can add to your profile on GitHub \(or BitBucket, GitLab, or your private enterprise Git server\). The public part:![](media/img(4).png)
2.  Copy your SSH key and paste it into your GitHub \(or other\) settings under SSH Keys.

    1. Click on your icon, and then click **Settings**.

    2. Click **SSH and GPG keys**.

    3. Click **New SSH key**, enter a description, and then paste your SSH key.

    Let me know if you have any questions on this!\}


Or for Bitbucket:

1. Click on your icon.

2. Click **Bitbucket settings**.

3. Click **SSH keys**.

4. Click **Add key**, enter a title, and then paste your SSH key where directed.

![](media/img(6).png)

Or for GitLab:

1. Click the User Settings icon in the upper right-hand corner.

2. From the drop-down menu, select **Settings**.

3. Click **SSH Keys**.

4. Paste your key, enter a title, and then click **Add key**.

![](media/img(7).png)

**Parent topic:**[zOS\_ISPF\_Git\_Interface\_Users\_Guide\_V3R0\_d5e1.html](zOS_ISPF_Git_Interface_Users_Guide_V3R0_d5e1.html)

