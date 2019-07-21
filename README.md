vench.sh
=========================

Forked from https://github.com/n-st/nench

- loosely based on the established freevps.us/bench.sh
- includes CPU and ioping measurements
- has a 10-second timeout for each speedtest, so you don't end up waiting 10
  minutes for that one slow speedtest from halfway around the globe — but
  thanks to the power of `curl -w`, you still get to see what speed your server
  achieved during those 10 seconds
- successfully tested on Arch Linux, Debian, FreeBSD, and Ubuntu
- reduced number of speedtests to 3 x 100MB
- IPv6 speedtest removed

Usage example
-------------

```
wget -qO- raw.githubusercontent.com/musthari/vench/master/vench.sh | bash 2>&1 | tee vench.log
```

Example output
--------------

```
-------------------------------------------------
 vench.sh v0.1 -- https://github.com/musthari/vench
 benchmark timestamp:    2019-07-21 09:43:20 UTC
-------------------------------------------------

Processor:    Intel(R) Xeon(R) CPU E3-1275 v5 @ 3.60GHz
CPU cores:    4
Frequency:    3600.030 MHz
RAM:          1.0G
Swap:         -
Kernel:       Linux 2.6.32-042stab134.3 x86_64

Disks:
Filesystem     Type      Size Inodes
/dev/simfs     simfs      15G   7.5M

CPU: SHA256-hashing 500 MB
    3.125 seconds
CPU: bzip2-compressing 500 MB
    5.133 seconds
CPU: AES-encrypting 500 MB
    0.855 seconds

ioping: seek rate
    min/avg/max/mdev = 87.9 us / 156.6 us / 6.45 ms / 212.7 us
ioping: sequential read speed
    generated 7.55 k requests in 5.00 s, 1.84 GiB, 1.51 k iops, 377.7 MiB/s


IPv4 speedtests
    your IPv4:    x.x.x.xxxx

    VULTR New Jersey:         22.86 MiB/s
    VULTR Frankfurt:        89.13 MiB/s
    VULTR Singapore:   7.23 MiB/s

-------------------------------------------------
```
