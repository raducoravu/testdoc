# Convert Repository \(CONVREPO\)

The convert repository command converts a repository that has been cloned into the users OMVS filesystem into a repository that ZIGI can manage. There are numerous requirements for ZIGI to be able to manage a repository, primarily because Git has no awareness of the z/OS datasets. All Git files are stored in an OMVS filesystem.

To be a ZIGI -managed repository requires the following:

1.  A .zigi directory in the repository root directory
2.  A file with the name of dsn in the .zigi directory with information on the z/OS datasets managed by ZIGI:

\# Default DSORG and DCB info

\* PO FB 80 32720

SAMPLE.REXX PO VB 255 32760

SAMPLE.PDS PO FB 80 32760

SAMPLE.TEXT PS FB 121 27951

1.  Each z/OS sequential datasets must have a copy in the repository root directory.
2.  Each z/OS partitioned dataset must have a directory in the repository root.
3.  Each PDS member must have a copy in the directory associated with the full PDS.
4.  Only files that are uppercase and conform to z/OS dataset naming conventions are accepted by ZIGI to be copied to z/OS.

The conversion process:

1.  Creates a .gitattributes file in the repository root directory if one does not exist. If a .gitattributes exists in the repository then it is untouched, but you should consider updating it with some of the .gitattributes that you can find in ZIGI managed repositories.
2.  Creates a .zigi subdirectory.
3.  Creates a .zigi/dsn file with a set of defaults.
4.  Identifies files in the repository root that conform to z/OS dataset naming conventions, after being translated to uppercase, and copies them to z/OS datasets using the high-level-qualifier defined when the repository was cloned.
5.  Identifies directories in the repository root that conform to z/OS dataset naming conventions after being translated to uppercase.
    1.  Creates a PDS in z/OS.
    2.  Renames the members within to remove any suffix to files with uppercase names assuming the file conforms to z/OS PDS member naming conventions.
    3.  Copies renamed files to the PDS as members.
6.  Files that end with .bin are treated as binary files and the .bin suffix is removed when copied to z/OS.

**Parent topic:**[The ZIGI Current Repository Panel](zOS_ISPF_Git_Interface_Users_Guide_V3R0_the_zigi_current_repository_panel.html)

