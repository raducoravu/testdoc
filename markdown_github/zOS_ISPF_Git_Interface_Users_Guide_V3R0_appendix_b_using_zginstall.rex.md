# Appendix B: Using ZGINSTALL.REX

The zginstall.rex is a generic installation tool that will work with any ZIGI managed repository to recreate the z/OS datasets when a repository is cloned outside of ZIGI. It is intended for use when a site does not have ZIGI installed on z/OS to allow ZIGI managed repositories to be installed easily.

To add zginstall.rex to a repository use the SET command in the Current Repository and update the settings thus:

![](media/img(85).png)

Which will generate a short and long message:

![](media/img(86).png)

A ‘git add’ is performed automatically. A Commit and Push should now be performed to lock in this update.

**Parent topic:**[zOS\_ISPF\_Git\_Interface\_Users\_Guide\_V3R0\_d5e1.html](zOS_ISPF_Git_Interface_Users_Guide_V3R0_d5e1.html)

