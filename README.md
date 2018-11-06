# Notes for Getting Started in HLab

## FiC 
### Generate SSH Keys
...
Use the key to access zeus:
- `ssh -XY zeus`
- `ssh fic0x`

### Setting up the Environment
- open terminal and type `nano ~/.bashrc`
- add `source /home/cad/xilinx/Vivado-2017.2/Vivado/2017.2/settings64.sh` to the file
    - try to use same version of the Vivado software
- type `vivado` or `vivado_hls` to bring up GUI
- in Vivado use `xcku095-ffvb2104-1-c` as default part

### TODO
There is currently no full automation for project setup, a manual copy-paste is needed. Designed HLS modules have to be imported as IPs and added under `warp`
 
### Resources
- Vivado HLS tutorial & User Guide

### Trouble shooting
- when HLS GUI can not be brought up
    - `sudo rm -rf .vivado_hls/2017.2/`
