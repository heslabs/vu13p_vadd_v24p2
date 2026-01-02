# Launch Emulation

---
### Resource
* Vitis Reference Guide (UG1702)
   * https://docs.amd.com/r/en-US/ug1702-vitis-accelerated-reference/Output-Directories-of-v-c-mode-aie
* XSCT to Python API migration
    * https://docs.amd.com/r/en-US/ug1400-vitis-embedded/XSCT-to-Python-API-migration
* Github: Xilinx/embeddedsw/lib/bsp/standalone/src/common
    * https://github.com/Xilinx/embeddedsw/tree/master/lib/bsp/standalone/src/common
    
### Configure HAPS and Program the Bitstream


```
xauth nlist $DISPLAY | sed -e 's/^..../add /' | sudo xauth -f /root/.Xauthority source -
sudo -E ./run-E-CoreFlow.sh
```


### Connect to ZYNQ 
```
ssh xilinx@192.168.1.3 -X
```

---
###

<img width="1200" height="900" alt="image" src="https://github.com/user-attachments/assets/d18a608e-21fd-4952-a24d-bbf72ec9238d" />
<br><br>

<img width="1200" height="931" alt="image" src="https://github.com/user-attachments/assets/dcd9c609-567b-4e94-9a29-d3dde8d54a30" />
<br><br>

<img width="1200" height="937" alt="image" src="https://github.com/user-attachments/assets/7cbe8086-02e0-41b4-b6e0-d584f137c855" />
<br><br>

<img width="1200" height="903" alt="image" src="https://github.com/user-attachments/assets/5f6dd270-128e-41eb-8dd9-a5693bbf6562" />
<br><br>
