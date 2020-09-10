# Creating a new Repository \(Local and Remote\)

There are two ways of creating a \(Git-based\) repository with ZIGI. Cloning \(see further\) a remote repository or creating one “from scratch” locally. Via the ‘create’ command a new \(local\) repository van be created. This performs a ‘git init <repoName\>’ in the chosen directory. A ‘basic’ .gitattributes is created and added/committed to your repository. This is there to make sure that the encoding of the various Git-managed files are in the correct format.

After creating the local repo \(remember ZIGI takes care of your .gitatrtibutes file\) you can ADD datasets to the repository. \(See the Add command on page xxx\).

Adding files to ZIGI is *not the same thing* as adding them to the Git-repository. Once a dataset has been added to ZIGI, the datasets \(in file-format\) are *only* available in the working-space of the Git repository. \(They are present in /repofolder/reponame\). Adding to the Git-repo is done via the A \(add\) line command.

**Parent topic:**[Typical ZIGI Activities](zOS_ISPF_Git_Interface_Users_Guide_V3R0_typical_zigi_activities.md)

