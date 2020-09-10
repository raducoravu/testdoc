# ZGBATCH -Execute ZIGI in Batch

There may be projects where there is a need to schedule ZIGI to check for updated, and new, elements in a repositories z/OS datasets. That is where ZGBATCH is used.

Sample JCL:

//ZGBATCH JOB XXX,’ZIGI’,REGION=0M,NOTIFY=&SYSUID

//OUT OUTPUT DEFAULT=YES,JESDS=ALL,OUTDISP=\(HOLD,HOLD\)

//\* -------------------- \*

//\* INVOKE ISPF IN BATCH \*

//\* -------------------- \*

//ISPF EXEC PGM=IKJEFT1B,DYNAMNBR=50

//\* -------------------------------- \*

//\* SYSEXEC IS WHERE THE CMD RESIDES \*

//\* -------------------------------- \*

//SYSEXEC DD DISP=SHR,DSN=*zigi.exec*

//\* ------------------------------- \*

//\* MLIB AND TLIB FOR THE REAL ISPF \*

//\* ------------------------------- \*

//ISPMLIB DD DISP=SHR,DSN=*ISP.SISPMENU*

//ISPTLIB DD DISP=SHR,DSN=*ISP.SISPTENU*

//\* ------------------------------------------------------ \*

//\* TEMPORARY PANELS, SKELETONS, AND TABLES ISPF LIBRARIES \*

//\* ALLOCATED TO VIO \*

//\* ------------------------------------------------------ \*

//ISPPLIB DD DISP=\(,DELETE\),SPACE=\(TRK,\(1,1,1\)\),UNIT=VIO,

// DCB=\(RECFM=FB,LRECL=80,BLKSIZE=6160\)

//ISPSLIB DD DISP=\(,DELETE\),SPACE=\(TRK,\(1,1,1\)\),UNIT=VIO,

// DCB=\(RECFM=FB,LRECL=80,BLKSIZE=6160\)

//ISPPROF DD DISP=\(,DELETE\),SPACE=\(TRK,\(1,1,1\)\),UNIT=VIO,

// DCB=\(RECFM=FB,LRECL=80,BLKSIZE=6160\)

//SYSTSPRT DD SYSOUT=\*

//\* ----------------------------------------------- \*

//\* SYSTSIN - THE BATCH TSO COMMANDS TO INVOKE ISPF \*

//\* ----------------------------------------------- \*

//SYSTSIN DD \*

PROFILE PREFIX\(*userid*\)

ispf cmd\(%zgbatch *repo-prefix**qualignr repo-directory P*

/\*

The zgbatch syntax is:

|Parameter|Description|
|Repo-prefix|This is the ZIGI define z/OS Prefix for the z/OS datasets within the repository|
|Qualignr|The \# of qualifiers to ignore when constructing the OMVS filenames|
|Repo-directory|The OMVS directory where the repository is located|
|C or P|C to commit only or

 P to commit and push

|

**Parent topic:**[zOS\_ISPF\_Git\_Interface\_Users\_Guide\_V3R0\_d5e1.md](zOS_ISPF_Git_Interface_Users_Guide_V3R0_d5e1.md)

