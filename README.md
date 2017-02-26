nench.sh ("new bench.sh")
=========================

Current version always available at https://github.com/n-st/nench

- loosely based on the established freevps.us/bench.sh
- includes CPU and ioping measurements
- reduced number of speedtests (9 x 100 MB), while retaining useful European
  and North American POPs
- runs IPv6 speedtest by default (if the server has IPv6 connectivity)

Usage example
-------------

```
(curl -s bench.wget.racing | bash; curl -s bench.wget.racing | bash) 2>&1 | tee nench.log
```

```
(wget -qO- bench.wget.racing | bash; wget -qO- bench.wget.racing | bash) 2>&1 | tee nench.log
```