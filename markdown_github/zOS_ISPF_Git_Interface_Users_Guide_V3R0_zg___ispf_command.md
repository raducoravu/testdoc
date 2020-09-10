# ZG – ISPF Command

There are times when an element is being edited \(updated\) within a PDS that is part of a ZIGI managed repository. After completing the update, just that element needs to be processed by Git. To edit an element, use the ZG command.

The syntax is: ZG dataset\(member\) option

Where: dataset\(member\) is the element to be quickly processed by Git.

Options:

|blank|Prompt for option|
|A|Git Add|
|AC|Git Add and Commit|
|ACP|Git Add, Commit and Push|

For ease of use, ZG may be entered on the ISPF member list row command next to the member name to be processed.

,’;\[![](media/img(80).png)

If the ZG command has not been used before for this dataset, then a list of all ZIGI managed repositories are presented from which to select:

![](media/img(81).png)

If ZG has been used with that dataset before, then the repository prompt is bypassed, and the short pop-up prompt appears:

![](media/img(82).png)

There is an additional option available via the pop-ups – O – which opens the repository.

**Parent topic:**[zOS\_ISPF\_Git\_Interface\_Users\_Guide\_V3R0\_d5e1.html](zOS_ISPF_Git_Interface_Users_Guide_V3R0_d5e1.html)

