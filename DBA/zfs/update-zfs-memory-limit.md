1. Check current arcsz

    `arcstat`

1. Modify `/etc/modprobe.d/zfs.conf`
   
   `echo "options zfs zfs_arc_max=214748364" >> /etc/modprobe.d/zfs.conf`
    
    *214748364 is 200M in bytes*

1. Modify `/sys/module/zfs/parameters/zfs_arc_max`
   
   `echo 214748364 > /sys/module/zfs/parameters/zfs_arc_max`
    
1. Update current initramfs

    `update-initramfs -u`

1. Check arcsz to confirm the modification takes effect
  
    `arcstat 1`
