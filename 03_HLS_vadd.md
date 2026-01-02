# Visit HLS IP Package

---
### Resource
* Vitis HLS Design Flow Lab
  * https://xilinx.github.io/xup_high_level_synthesis_design_flow/Lab1.html

---
### Tcl

```
create_project hls /home/demo/haps/vu13p/vu13p_vadd_v24p2/vivado/hls -part xcvu13p-fhgb2104-2-e
update_ip_catalog
add_files -norecurse {/home/demo/haps/vu13p/vu13p_vadd_v24p2/src/vadd/vadd_B_BUS_m_axi.v /home/demo/haps/vu13p/vu13p_vadd_v24p2/src/vadd/vadd_A_BUS_m_axi.v /home/demo/haps/vu13p/vu13p_vadd_v24p2/src/vadd/vadd_CTRL_BUS_s_axi.v /home/demo/haps/vu13p/vu13p_vadd_v24p2/src/vadd/vadd_C_BUS_m_axi.v /home/demo/haps/vu13p/vu13p_vadd_v24p2/src/vadd/vadd.v}
import_files -force -norecurse
update_compile_order -fileset sources_1
create_peripheral user.org user myip 1.0 -dir /home/demo/haps/vu13p/vu13p_vadd_v24p2/vivado/ip_repo
add_peripheral_interface S00_AXI -interface_mode slave -axi_type lite [ipx::find_open_core user.org:user:myip:1.0]
generate_peripheral -driver -bfm_example_design -debug_hw_example_design -force [ipx::find_open_core user.org:user:myip:1.0]
write_peripheral [ipx::find_open_core user.org:user:myip:1.0]
set_property  ip_repo_paths  {/home/demo/haps/vu13p/vu13p_vadd_v24p2/vivado/ip_repo/myip_1_0 /home/demo/dla/zcu104dla_v24p2/source/RTL_nv_small_07} [current_project]
update_ip_catalog -rebuild
set_property top vadd [current_fileset]
update_compile_order -fileset sources_1
ipx::package_project -root_dir /home/demo/haps/vu13p/vu13p_vadd_v24p2/vivado/ip_repo -vendor user.org -library user -taxonomy /UserIP -import_files
ipx::associate_bus_interfaces -busif m_axi_A_BUS -clock ap_clk [ipx::current_core]
set_property core_revision 2 [ipx::current_core]
ipx::create_xgui_files [ipx::current_core]
ipx::update_checksums [ipx::current_core]
ipx::check_integrity [ipx::current_core]
ipx::save_core [ipx::current_core]
set_property  ip_repo_paths  {/home/demo/haps/vu13p/vu13p_vadd_v24p2/vivado/ip_repo /home/demo/haps/vu13p/vu13p_vadd_v24p2/vivado/ip_repo/myip_1_0} [current_project]
```

---
### Create Vivado Project

<img width="1200" height="776" alt="image" src="https://github.com/user-attachments/assets/deadcf77-39f5-4c0f-992d-9c9a908022da" />
<br><br>

<img width="650" height="500" alt="image" src="https://github.com/user-attachments/assets/e128b89e-107a-4f37-8433-fdb90d6e8137" />
<br><br>

---
### Create and Package New IP 
<img width="1200" height="1285" alt="hls-01" src="https://github.com/user-attachments/assets/da1dd008-0adf-41ba-a089-3154b6d78b2b" />
<br><br>


<img width="650" height="412" alt="image" src="https://github.com/user-attachments/assets/273da08e-d868-4b01-912d-8b26df9bd7ac" />
<br><br>

<img width="650" height="708" alt="image" src="https://github.com/user-attachments/assets/485c3d9a-4004-4161-95be-7df08b08454b" />
<br><br>

<img width="650" height="611" alt="image" src="https://github.com/user-attachments/assets/0f6407bf-5e5d-455c-8468-a093e2997fdf" />
<br><br>

<img width="650" height="611" alt="image" src="https://github.com/user-attachments/assets/62692e0d-93f0-4832-a71e-2efcf47963ed" />
<br><br>

<img width="650" height="776" alt="image" src="https://github.com/user-attachments/assets/de525eca-cad8-41a9-8a31-481130099d0e" />
<br><br>

---
### Set IP Top

<img width="1200" height="1480" alt="hls-02" src="https://github.com/user-attachments/assets/3587c290-6b27-4f8b-bf9d-181ac3787f2d" />
<br><br>

<img width="1200" height="1297" alt="hls-03" src="https://github.com/user-attachments/assets/f57a1bc8-ab61-4a67-85ca-cca20d119268" />
<br><br>

<img width="800" height="783" alt="image" src="https://github.com/user-attachments/assets/f065f130-afdd-429d-88fe-930cec85dc22" />
<br><br>

<img width="1997" height="1178" alt="image" src="https://github.com/user-attachments/assets/8e857c68-5b89-40ca-a731-2ac251c1a9bc" />
<br><br>

<img width="1200" height="1135" alt="image" src="https://github.com/user-attachments/assets/138017f1-e822-43fa-a384-e039f951a6bf" />
<br><br>
