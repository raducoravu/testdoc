# Using Git

1.  Create an account at GitHub.com and add your \(Mainframe\) SSH Public-Key to your account.
2.  If you have not added your SSH keys to your GitHub settings, then provide your username and password at the prompt.

    It is highly recommended that you add your public SSH key to your GitHub account settings to eliminate the prompts for userid and password.

3.  Sign into OMVS and change to a directory from where you are installing ZIGI.
4.  If your SSH key is already generated and added to your GitHub account, execute the following command:

git clone git@github.com:wizardofzos/zigi.git

cd zigi

sh install.sh

If you haven’t added your SSH key to Github clone via https

git clone https://github.com/wizardofzos/zigi.git

\[provide GitHub username and password when prompted\]

cd zigi

sh install.sh

Should you not have the option to connect from your Mainframe directly to GitHub you can download the zip files, unzip them, upload them to your mainframe, and then run the installer. The latest stable version of ZIGI can be downloaded from https://github.com/wizardofzos/zigi/

When running the zginstall.rex script there are a few prompts asking for a high-level-qualifier for the ZIGI ISPF datasets to be created under. The ZIGI partitioned datasets are allocated as PDSE partitioned datasets.

After the zginstall.rex completes, exit OMVS and return to native ISPF and execute the ZGSTAT exec as documented in the zginstall.rex report. That will apply the ISPF statistics to the PDS members of ZIGI.

To use the ZG command, it must be copied from the ZIGI.EXEC library into a library in the standard SYSEXEC, or SYSPROC, allocation.

For more information check out the ZIGI wiki at [https://github.com/wizardofzos/zigi/wiki](https://github.com/wizardofzos/zigi/wiki).

**Parent topic:**[Installing ZIGI](zOS_ISPF_Git_Interface_Users_Guide_V3R0_installing_zigi.html)

