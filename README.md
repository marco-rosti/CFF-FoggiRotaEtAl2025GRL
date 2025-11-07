# Raw Data Repository

_This is the official repository containing the raw data supporting the analyses presented in_

**Effect of submerged vegetation on water surface geometry and air–water momentum transfer**  
_by Giulio Foggi Rota<sup>1</sup>, Alessandro Chiarini<sup>1,2</sup>, and Marco Edoardo Rosti<sup>1</sup>_

1: Complex Fluids and Flows Unit, Okinawa Institute of Science and Technology Graduate University, 1919-1 Tancha, Onna, Okinawa 904-0495, Japan  
2: Dipartimento di Scienze e Tecnologie Aerospaziali, Politecnico di Milano, via La Masa 34, 20156 Milano, Italy  

*XXX Add reference to the manuscript once published XXX*  

---

## **Data Structure**

We report data from our simulations over a smooth and a vegetated bed, contained in the respectively named folders.  

Each folder includes:  
* A subfolder named **_interface_**, containing interface elevation snapshots saved every time unit after reaching steady state.  
  Files are stored in `.vtk` format and can be visualized with **ParaView**.  
* A text file named **_stats_fluid.out_** containing averaged flow statistics from the steady state.  
  The file is organized in columns as follows:  
  ```
  z, um, vm, wm, pm, u2, v2, w2, p2, uv, uw, vw
  ```
  where  
  - `z`: wall-normal coordinate  
  - `um`, `vm`, `wm`, `pm`: mean flow and pressure profiles  
  - `u2`, `v2`, `w2`, `p2`: mean square profiles of flow and pressure fluctuations  
  - `uv`, `uw`, `vw`: turbulent shear stress profiles  

* A text file named **_stats_vof.out_** containing averaged volume-of-fluid (VOF) statistics from the steady state.  
  The file is organized in columns as follows:  
  ```
  z, vof1m, vof2m,
  vof1um, vof1vm, vof1wm, vof1pm,
  vof1u2, vof1v2, vof1w2, vof1p2,
  vof1uv, vof1uw, vof1vw,
  vof2um, vof2vm, vof2wm, vof2pm,
  vof2u2, vof2v2, vof2w2, vof2p2,
  vof2uv, vof2uw, vof2vw
  ```
  where  
  - `vof1m`, `vof2m`: mean VOF profiles for the two fluid phases  
  - `vof1um`, `vof1vm`, `vof1wm`, `vof1pm`: mean flow and pressure profiles of VOF phase 1  
  - `vof1u2`, `vof1v2`, `vof1w2`, `vof1p2`: mean square profiles of VOF phase 1  
  - `vof1uv`, `vof1uw`, `vof1vw`: turbulent shear stress profiles of VOF phase 1  
  - `vof2um`, `vof2vm`, `vof2wm`, `vof2pm`: mean flow and pressure profiles of VOF phase 2  
  - `vof2u2`, `vof2v2`, `vof2w2`, `vof2p2`: mean square profiles of VOF phase 2  
  - `vof2uv`, `vof2uw`, `vof2vw`: turbulent shear stress profiles of VOF phase 2  

---

### **Notes**

All reported data are in **code units**, based on a unitary water depth and a gravity vector of magnitude **0.36**.  
All profiles specific to a single fluid phase should be rescaled by the corresponding VOF concentration; for example, the mean velocity profile of the water phase is obtained as  
```
vof1vm / vof1m
```

`u`, `v`, and `w` represent the velocity components in the **spanwise**, **streamwise**, and **vertical** directions, respectively.
