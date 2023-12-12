These files are the example /etc/xen/$DOMU.cfg files I use for booting Xen domUs.  The paths for disks are set to
match the LVM configuration in [xen-preseed.cfg](tftp/xen-preseed.cfg).  

The top three options are useful during initial installation/reinstall of the domUs, and once the LVM path has been 
installed to, they should be commented out and the bootloader line uncommented.  At that point you can create the 
domU and it will run normally.
