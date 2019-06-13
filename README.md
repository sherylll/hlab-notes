# Notes for Getting Started in HLab

## Playing with Zedboard
`sudo screen /dev/ttyACM0 115200` to log into linux
`reset` might fix random character issues

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

### Generate bitstream
- find bitfile under `runs/imp/xxx.bit`
- run `bitgen.tcl` in vivado CLI

### TODO
There is currently no full automation for project setup, a manual copy-paste is needed. Designed HLS modules have to be imported as IPs and added under `wrap`
 
### Resources
- Vivado HLS tutorial & User Guide
- Hunga's tutorials can be found under `/asap/fic/proj_hunga/pr_base/rasbpi`

### Trouble shooting
- when HLS GUI can not be brought up
    - `sudo rm -rf .vivado_hls/2017.2/`

## RETURNN
### Tensorflow
Used conda + python 3.6 + tensorflow with GPU support

### GPU Usage
`ssh -XY nova`
- To switch CUDA version, modify `PATH`:
```
export PATH=${PATH}:/usr/local/cuda-9.0/bin
export CUDA_HOME=${CUDA_HOME}:/usr/local/cuda:/usr/local/cuda-9.0
export LD_LIBRARY_PATH=${LD_LIBRARY_PATH}:/usr/local/cuda-9.0/lib64
export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/usr/local/cuda/extras/CUPTI/lib64
```
However it is easier to install a different version of tf than cuda, see version mapping:
https://www.tensorflow.org/install/source#linux

### Compiling error when using nvcc
Solved by adding `-DNDEBUG` to the compiling command.

### trained model
Trained models can be found under `/tmp/hikari/crnn`, can be configure in `.config` file.

## System
When login cannot be performed on Atlantis:
- login from another machine
- `sudo gedit /lib/systemd/system/systemd-logind.service` and comment out `IPAddressDeny=any`
- `sudo systemctl daemon-reload`
