This configuraton is based on the debian-installer [netboot](https://deb.debian.org/debian/dists/bookworm/main/installer-amd64/current/images/netboot/) tarball.  
Simply download the netboot.tar.gz file and untar it to your tftp root.  The files in this repo are written with this in mind.

The boot configs in this repo should be placed in the $TFTP_ROOT/pxelinux.cfg/ folder of your tftp server that the netboot tarball creates.

You can specify which hosts use which boot configs by renaming the boot configuration file 01-$MAC_ADDRESS (i.e. "01-00-16-3e-00-00-01" for a Xen domU with that
given MAC address), or by naming it "default".  When a client is pxebooted, it will search for the client's UUID, then "01-$MAC_ADDRESS", then a descending search on
the hexidecimal uppercase ip address of the client, removing a single character and searching again for the next, until finally loading "default" if no hexidecimal
characters remain of the ip address.  See: [syslinux pxelinux documentation](https://wiki.syslinux.org/wiki/index.php?title=PXELINUX#Configuration) for more details.
