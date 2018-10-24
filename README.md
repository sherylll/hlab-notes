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

### Resources
- Vivado HLS tutorial & User Guide

### Trouble shooting
- problem with Vivado license
    - delete some file (?)
