# Validation of BBR Congestion Control in ns-3 vs Linux

This repository contains the files to validate the implementation of BBR in ns-3 vs its implementation in Linux.

Note: Ubuntu 20.04 was used for this work.

### Steps to generate ns-3 plot
* Clone the ns-3-dev repository: `https://gitlab.com/nsnam/ns-3-dev`
* Installation steps are described here: `https://www.nsnam.org/wiki/Installation#Ubuntu.2FDebian.2FMint`
* Copy `tcp-bbr-example.cc` from the `ns-3 scripts` directory provided in this repository and paste it in `ns-3-dev/scratch`
* Copy `Plot Scripts` directory from the `ns-3 scripts` directory provided in this repository and paste it in the ns-3 root directory (i.e., in parallel to `src` or `scratch`)
* Run `tcp-bbr-example.cc` using the following command:
```shell
./waf --run scratch/tcp-bbr-example
```
* The results will be stored in a new directory called `bbr-results`
* Plot the congestion window graph using `gnuplotScriptCwnd` and `cwnd.plotme`

## Final Result
![Final graph](https://github.com/mohittahiliani/BBR-Validation/blob/main/Final%20plot/cwnd.png?raw=true)
