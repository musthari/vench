vench.sh
=========================

Forked from https://github.com/n-st/nench

- loosely based on the established freevps.us/bench.sh
- includes CPU and ioping measurements
- reduced number of speedtests (9 x 100 MB), while retaining useful European
  and North American POPs
- runs IPv6 speedtest by default (if the server has IPv6 connectivity)
- has a 10-second timeout for each speedtest, so you don't end up waiting 10
  minutes for that one slow speedtest from halfway around the globe — but
  thanks to the power of `curl -w`, you still get to see what speed your server
  achieved during those 10 seconds
- successfully tested on Arch Linux, Debian, FreeBSD, and Ubuntu

Usage example
-------------

```
wget -qO- raw.githubusercontent.com/musthari/vench/master/vench.sh | bash 2>&1 | tee vench.log
```

Example output
--------------

Output from a VPS hosted with Vultr in Frankfurt:

```

```
