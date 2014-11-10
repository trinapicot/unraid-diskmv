unraid-diskmv
=============

A set of utilities to move unRAID user share directories between disks. Currently consists of two bash scripts:

* `diskmv` will move a user share directory from one disk to another. It uses a find/rsync command similar to what is found in the standard mover script. It is suitable for merging a user share directory onto a disk that already contains that directory.  Files that have duplicate file names  on the destination disk will not moved.
* `consld8` can consolidate a user share directory from multiple disks onto one disk. If a destination disk is not specified, it will pick the best disk based on max usage and available space.  By default, consld8 will run in test mode and display some information about how directories would be moved, but will not actually move files unless forced. `diskmv` is required to actually move files.

Example usage:

    diskmv "/mnt/user/video/tv/Pushing Daisies" disk4 disk1
    
    consld8 /mnt/user/video/tv/Wonderfalls disk3

These utilities move files around on an unRAID server. I have done my best to 
prevent any data loss, but there is always a chance something can go wrong. Use at your own risk and please ensure you have everything backed up.
