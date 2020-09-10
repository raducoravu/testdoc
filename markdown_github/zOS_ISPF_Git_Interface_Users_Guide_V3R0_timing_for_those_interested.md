# Timing \(For Those Interested\)

For those who may be interested in some of the internal timings, it is as easy as allocating a DD with the name of ZIGIDEBG. When ZIGI runs, time stamps for various routines and functions are recorded in a file in the user’s home directory. When ZIGI ends, if the DD was allocated, the file is listed in UDList:

![](media/img(83).png)

The file may be browsed, viewed, edited, or deleted.

![](media/img(84).png)

The active debug log may be viewed from several of the panels \(Local Repository, Current Repository, and PDS Member List\) by using the **VIEWD** command.

For those interested, here is a short EXEC that allocates and/or frees the ZIGIDEBG DD:

/\* ------------------- REXX ---------------------- \*

\| A toggle exec that will allocate the ZIGIDEBG DD \|

\| if it does not exist and if it does then it will \|

\| be freed. \|

\* ------------------------------------------------ \*/

x = listdsi\('ZIGIDEBG' 'FILE'\)

if x \> 0 then if sysreason = 3 then 'Free F\(ZIGIDEBG\)'

else 'Alloc f\(zigidebg\) dummy reuse'

**Parent topic:**[zOS\_ISPF\_Git\_Interface\_Users\_Guide\_V3R0\_d5e1.md](zOS_ISPF_Git_Interface_Users_Guide_V3R0_d5e1.md)

