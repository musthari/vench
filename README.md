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
- dd test removed

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
 benchmark timestamp:    2019-07-21 09:52:25 UTC
-------------------------------------------------

Processor:    Intel(R) Core(TM) i7-7700K CPU @ 4.20GHz
CPU cores:    3
Frequency:    4200.000 MHz
RAM:          3.9G
Swap:         1.0G
Kernel:       Linux 4.9.0-9-amd64 x86_64

Disks:
vda     50G  HDD

CPU: SHA256-hashing 500 MB
    1.964 seconds
CPU: bzip2-compressing 500 MB
    3.245 seconds
CPU: AES-encrypting 500 MB
    0.614 seconds

ioping: seek rate
    min/avg/max/mdev = 65.5 us / 374.8 us / 3.10 ms / 142.9 us
ioping: sequential read speed
    generated 5.87 k requests in 5.00 s, 1.43 GiB, 1.17 k iops, 293.4 MiB/s


IPv4 speedtests
    your IPv4:    139.99.55.xxxx

    VULTR New Jersey:         9.10 MiB/s
    VULTR Frankfurt:          12.46 MiB/s
    VULTR Singapore:          75.65 MiB/s

-------------------------------------------------
```
