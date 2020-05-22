1. Install `zfsutils`

    `sudo apt-get install zfsutils-linux -y`
    
2. Check disk name&path

    `df -l`
    
    
        Filesystem     1K-blocks    Used Available Use% Mounted on
        udev              491520       0    491520   0% /dev
        tmpfs             100732     816     99916   1% /run
        /dev/xvda1       8065444 1706288   6342772  22% /
        tmpfs             503648       8    503640   1% /dev/shm
        tmpfs               5120       0      5120   0% /run/lock
        tmpfs             503648       0    503648   0% /sys/fs/cgroup
        /dev/loop0         96128   96128         0 100% /snap/core/8935
        /dev/loop1         18432   18432         0 100% /snap/amazon-ssm-agent/1566
        tmpfs             100728       0    100728   0% /run/user/1000
    
    
    
    `lsblk`
    
        loop0     7:0    0 93.8M  1 loop /snap/core/8935
        loop1     7:1    0   18M  1 loop /snap/amazon-ssm-agent/1566
        xvda    202:0    0    8G  0 disk
        └─xvda1 202:1    0    8G  0 part /
        xvdb    202:16   0    8G  0 disk
        ├─xvdb1 202:17   0    8G  0 part
        └─xvdb9 202:25   0    8M  0 part

3. Create zpool
  
    `zpool create citus /dev/xvdb`
    
4. Set compression

    `zfs set compression=gzip citus`
    
5. Check config
    
    `zfs get all citus`
    
    
    
    
