# Visit HLS IP - vmul

 
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

--
### Create Vivado Project

<img width="1200" height="776" alt="image" src="https://github.com/user-attachments/assets/deadcf77-39f5-4c0f-992d-9c9a908022da" />
<br><br>

<img width="650" height="500" alt="image" src="https://github.com/user-attachments/assets/e128b89e-107a-4f37-8433-fdb90d6e8137" />
<br><br>

---
### Create and Package New IP 
<img width="1200" height="1285" alt="hls-01" src="https://github.com/user-attachments/assets/da1dd008-0adf-41ba-a089-3154b6d78b2b" />
<br><br>
 
