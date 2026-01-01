# HAPS VU13P

<img width="600" height="504" alt="image" src="https://github.com/user-attachments/assets/b2dd83ec-48be-4a44-9c5e-f701d9c23855" />
<img width="150" height="132" alt="image" src="https://github.com/user-attachments/assets/2fa62161-8c33-41dd-99cc-c8986b95fed4" />
<img width="250" height="89" alt="image" src="https://github.com/user-attachments/assets/b8f3c26e-95a6-43ca-b180-7a2bf4291bf3" />

---
### Features
* 1 Xilinx Virtex UltraScale+ XCVU13P FHGB2104 FPGA
* Selectable I/O voltage for HapsTrak 3 daughter board slots
* Configurable global clocks
* Real-time monitoring of voltage/current and temperature
* Physical JTAG Programming
* Xilinx Virtual Cable Programming
* 4 samtec APF6 connector (72 pairs GTY transceivers)
* 10 HapsTrak 3 connectors
* 1 on-board DDR4 16bit SDRAM 1GB
* 1 PMOD connectors
* QSFP supports applications up to 28G
* RJ45 10/100/1000M RGMII PHY chip(88E1518)


---
### Block Diagram
<img width="600" height="867" alt="image" src="https://github.com/user-attachments/assets/96837013-f89b-4063-ae25-fa37abb4d3f7" />
<br><br>

### I/O Signals and Connections
<img width="650" height="717" alt="image" src="https://github.com/user-attachments/assets/3527a970-bd5a-40db-ab52-ff979e868c96" />
<br><br>

### Main Board Laypout: Top View
<img width="800" height="1027" alt="image" src="https://github.com/user-attachments/assets/9f5f3c7d-af85-4fdb-8d13-d539a9e5e397" />
<br><br>

### EPS-VU13P USer Panel
<img width="650" height="688" alt="image" src="https://github.com/user-attachments/assets/43ded654-5fdd-4a11-857c-a979f6bdda02" />
<br><br>

### Clocking

* Local Clocks
   * Local clocks on FPGAs are available through the **HapsTrak 3 (HT3)** connector.
   * Signals are differential, GC (Global Clock), GC_QBC (Global Clock,Quad-Byte Clock) and DBC (Dedicated-Byte Clock).
* Global Clocks
   * The EPS-VU13P system features 5 global clocks driven by on-board PLLs:
   * one PLL is dedicated to FPGA (**GCLK3**), while another PLL serves the FPGA for **GCLK0 to GCLK2** via the pin pair C1P/C1N on all 10 HT3 connectors.
   * Users can customize the EXT_GCLK (**GCLK4**) for the FPGA by connecting an external clock source via an MMCX connector.
   * All global clock nets utilize LVDS differential signaling for optimal performance.
   * The PLL input source is fixed at a 48MHz crystal.
   * The default frequencies for different components are as follows: FPGA (**VU13P_GCLK**) operates at **125MHz**
   * QSFP (**QSFP28_REFCLK**) operates at **156.25MHz**, and an output clock frequency range between 100Hz to 720MHz is achievable.
   * The on-board DDR4 (**C0_SYS_CLK_C**) operates at **200MHz**, and this frequency is non-configurable.

 
<br><br>
<img width="750" height="742" alt="image" src="https://github.com/user-attachments/assets/469a791d-6363-4f9d-9e69-df8bda8b02c5" />

### Clocks Constranits File
```
### pin.xdc
set_property PACKAGE_PIN BB9 [get_ports {gclk_clk_p[0]}]
set_property PACKAGE_PIN A20 [get_ports rst_btn]
set_property PACKAGE_PIN P11 [get_ports aurora_refclk_clk_p]
### SODIMM_HT3 JX1 JX2 JX3 <> EPS_VU13P  JX7 JX6 JX5
set_property -dict {PACKAGE_PIN AG31 IOSTANDARD LVCMOS12} [get_ports c0_ddr4_32G_reset_n]
set_property -dict {PACKAGE_PIN AE31 IOSTANDARD DIFF_SSTL12} [get_ports c1_sys_clk_clk_p]
set_property -dict {PACKAGE_PIN AE32 IOSTANDARD DIFF_SSTL12} [get_ports c1_sys_clk_clk_n]
set_property -dict {PACKAGE_PIN AH32 IOSTANDARD SSTL12_DCI OUTPUT_IMPEDANCE RDRV_40_40} [get_ports c0_ddr4_32G_act_n]
### DDR
set_property PACKAGE_PIN J14 [get_ports c0_sys_clk_clk_p]
set_property PACKAGE_PIN H14 [get_ports c0_sys_clk_clk_n]
set_property IOSTANDARD LVDS [get_ports {gclk_clk_p[0]}]
set_property IOSTANDARD LVCMOS18 [get_ports rst_btn]
create_clock -period 6.400 -name aurora_refclk_clk_p -waveform {0.000 3.200} [get_ports aurora_refclk_clk_p]
set_property IOSTANDARD DIFF_SSTL12 [get_ports c0_sys_clk_clk_p]
set_property IOSTANDARD DIFF_SSTL12 [get_ports c0_sys_clk_clk_n]
```

### Pin Assignment

<img width="900" height="652" alt="image" src="https://github.com/user-attachments/assets/b4e4d82a-6b8d-4c07-a9e2-8a87cca07edd" />
<br><br>
<img width="650" height="481" alt="image" src="https://github.com/user-attachments/assets/1209f21e-bba3-4e4d-b3d6-f3ccc69f314a" />
<br><br>
<img width="850" height="973" alt="image" src="https://github.com/user-attachments/assets/a3b09062-a108-46ac-9770-19d73e56ab24" />
<br><br>
<img width="850" height="1740" alt="image" src="https://github.com/user-attachments/assets/248d97c4-4e1f-48a8-aa21-ab38ab44df77" />
<br><br>
<img width="850" height="1319" alt="image" src="https://github.com/user-attachments/assets/05f6097f-4812-4901-83ff-83bbea6d1329" />
  
