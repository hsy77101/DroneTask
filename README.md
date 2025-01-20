# DroneTask

Wrote by syhwang / Date Jan 20th, 2025

[ Memo ]
Installed QT 6.8.1 on Widnows10 
Installed MS Visual Studio 2019 Version
(Downloaded files by google searching because it was not available in official web)
Installed Git Windows Version
Clone(Download) Source Code by gi

Problem : 
MSVC 2019 version is not available on QT 6.8.1 
even though wiki mentioned MSVC 2019 version with QT6.8.1. 

Check point to solve problem
1. folder location for Build

[ Daejeon Gwanpyeong-dong Long/Lat Coordinate ]
The followings are not available for Gazebo not Gazebo classic
export PX4_HOME_LAT=36.4345828
export PX4_HOME_LON=127.3947277
export PX4_HOME_ALT=28.5


[ How to run Gazebo Example ]

ex1)
make px4_sitl gz_standard_vtol_baylands

ex2)
PX4_SYS_AUTOSTART=4001 PX4_GZ_MODEL_POSE="0,2" PX4_SIM_MODEL=gz_x500 PX4_HOME_LAT=36.4345828 PX4_HOME_LON=127.3947277 PX4_HOME_ALT=28.5 ./build/px4_sitl_default/bin/px4


[ Multiple Drones Connection with Gazebo ]
PX4_SYS_AUTOSTART=4001 PX4_GZ_MODEL_POSE="0,2" PX4_SIM_MODEL=gz_x500 ./build/px4_sitl_default/bin/px4 -i 1
PX4_SYS_AUTOSTART=4001 PX4_GZ_MODEL_POSE="0,2" PX4_SIM_MODEL=gz_x500 ./build/px4_sitl_default/bin/px4 -i 2
PX4_SYS_AUTOSTART=4001 PX4_GZ_MODEL_POSE="0,2" PX4_SIM_MODEL=gz_x500 PX4_HOME_LAT=36.4345828 PX4_HOME_LON=127.3947277 PX4_HOME_ALT=28.5 ./build/px4_sitl_default/bin/px4 -i 3

[ Ref ]
https://docs.px4.io/main/en/sim_gazebo_gz/


[ How to use joystick with QgroundControl ]


[ How to make Shell Script ]
vi gazebo.sh

#!/bin/bash
echo "Run Gazebo with VTOL"
cd PX4_Autopilot
make px4_sitl gz_standard_vtol

chmod +x run_gazebo.sh
