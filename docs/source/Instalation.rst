Installation
============

.. _installation:

Installation
------------

To build the project:
* Install SUMO following the guide at [https://sumo.dlr.de/wiki/Downloads](https://sumo.dlr.de/wiki/Downloads)
* You can use 
    
`sudo add-apt-repository ppa:sumo/stable`  
`sudo apt update`  
`sudo apt install sumo sumo-tools sumo-doc`  
* Be careful: in the future the previous commands will install updated version of SUMO which are not ensured to work with this scripts (that are tested with any version from **v-1.6.0** to **v-1.18.0** )
* Test sumo by opening a terminal and running "sumo-gui".
	
* **Possible problems**:
			
You may get the following error when running SUMO:
			
"sumo-gui: symbol lookup error: /usr/lib/libgdal.so.26: undefined symbol: GEOSMakeValid_r"
    
To solve it, remove all the reference to GEOS inside /usr/local/lib/ (do NOT do it if you need the GEOS library):
    
"sudo rm /usr/local/lib/libgeos*"

* Clone this repository in your pc:

`git clone https://github.com/marcomali/ms-van3t`

* Run, from this repository either:

`./sandbox_builder.sh install-dependencies` -> if this is the first time you install ns-3 or ms-van3t on your system

or

`./sandbox_builder.sh` -> if this is **not** the first time you install ns-3 

This script will download the proper version of ns-3-dev and install this framework. The folder `ns-3-dev` will remain linked to this GitHub repository (not to the vanilla ns-3-dev one), allowing you to more easily develop updates and possibile contributions to *ms-van3t*.
    
* Configure `ns3` to build the framework with `<ns3-folder>./ns3 configure --build-profile=optimized --enable-examples --enable-tests --disable-python (add here what you want to enable)"` - The usage of the optimized profile allows to speed up the simulation time. This command should be launched from inside the `ns-3-dev` folder.

* **Important**: If you are compiling ms-van3t on Ubuntu 22.04 LTS or later, you need to specify, when calling `./ns3 configure`, also the `--disable-werror` flag

* Build ns3:
`./ns3 build`

**Important**

`src/automotive/` contains all the application related files and all the source code implementing the ETSI ITS-G5 stack for vehicular communications. Inside `sumo_files_v2v_map` you can find the SUMO map and trace for the V2V sample application, while inside `sumo_files_v2i_map` you can find the SUMO map and trace for the V2I sample application. Similarly you can find the SUMO map and trace for the Traffic Manager sample application inside `sumo_files_v2i_TM_map` and the ones for the Emergency Vehicle Warning inside `sumo_files_v2i_EVW_map`

`src/traci/` and `src/traci-applications/` contain instead all the logic to link ns-3 and SUMO. 

`src/cv2x/` contains the model for C-V2X in transmission mode 4.

The user is also encouraged to use the `sumo_files_v2v_map` and `sumo_files_v2i_map` folders to save there the SUMO-related files for his/her own applications.

**The version of CAM and DENM messages (v1 or v2)** can be easily switched by relying on the `switch_ETSI_version.sh` script. This script relies on the `ns-3-dev/src/automotive/model/ASN1/currmode.txt` file. Please **never** modify it manually or delete it!
