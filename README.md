# Validation of BBR Congestion Control in ns-3 vs Linux

This repository contains the files to validate the implementation of BBR in ns-3 vs its implementation in Linux.

Note: Ubuntu 20.04 was used for this work.

## Steps to generate ns-3 plot
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

## Steps to generate NeST plot
* Clone the NeST repository: `https://gitlab.com/nitk-nest/nest`
* Installation steps are described here: `https://gitlab.com/nitk-nest/nest/-/blob/master/INSTALL.md`
* Copy `tcp-bbr-example.py` from the `NeST scripts` directory provided in this repository and paste it in `nest/examples`
* Run `tcp-bbr-example.py` using the following command:
```shell
sudo python3 tcp-bbr-example.py
```
* The results will be stored in a new directory starting with a string `BBR_validation`
* The plot for congestion window is available in `ss` directory

## Final Result with overlapped plot
When the congestion window plots from ns-3 and NeST are overlapped, you should get the plot as shown below:

![Final graph](https://github.com/mohittahiliani/BBR-Validation/blob/main/Final%20plot/cwnd.png?raw=true)

## Acknowledgments
This work was a joint effort by the following students at National Institute of Technology Karnataka, Surathkal, India:
* ns-3 scripts were developed by Aarti Nandagiri and Vivek Jain
* NeST scripts were developed by Sushma Meena and Aditya Chaudhary

The details of BBR implementation in ns-3 are published in:

`Vivek Jain, Viyom Mittal and Mohit P. Tahiliani. "Design and Implementation of TCP BBR in ns-3." Proceedings of the 10th Workshop on ns-3. 2018.`

Link: `https://dl.acm.org/doi/10.1145/3199902.3199911`