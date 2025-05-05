# monospheres
This is the directory containing code for the Monospheres mapping and exploration pipeline, along with a custom version of the OpenVINS package modified for compatibility with the MRS system.
To run the MonoSpheres method example, run `monospheres/tmux_scripts/fireworld_monospheres/tmux.sh`.
To run the OctoMap mapper and random explorer approach used as baseline in the paper, run `monospheres/tmux_scripts/fireworld_monospheres/tmux.sh`.

To run both of these scripts, it is first needed to install the MRS sytem and build the packages in this repository. Please follow these instructions for installation:

1) Install ROS and the MRS UAV system as per the instructions at https://ctu-mrs.github.io/docs/installation/. We recommend to install natively (this requires Ubuntu 20.04), as the code has been tested only on computers with a native installation, but the apptainer variant should work as well (but all of the following instructions must be made in the apptainer in that case).
2) Create a ROS workspace (if it was not created by the MRS system installation already), add the packages contained in this repository (both the monospheres/ and dependecies/ folders) into your workspace's `src/` folder, build the workspace using `catkin_build` and source the workspace.
4) Install the required python packages for the monospheres package using the `./create_python_env.sh` script in the monospheres package.
5) Run `monospheres/tmux_scripts/fireworld_monospheres/tmux.sh`. This will launch a tmux session using the tmux config of the MRS system. If you want to use your own config or the default tmux keybindings, just comment out the line `tmux_options: -f /etc/ctu-mrs/tmux.conf` in `session.yaml`. Otherwise, the MRS system TMUX keybinds are available at https://github.com/ctu-mrs/mrs_cheatsheet?tab=readme-ov-file ).


## Troubleshooting
- If the UAV does not spawn at all, and  
