# gh auth login 설정 필요

`git clone -b jazzy https://github.com/ROBOTIS-GIT/DynamixelSDK.git`

`git clone -b jazzy https://github.com/ROBOTIS-GIT/dynamixel_interfaces.git`


`gh repo list Robit-humanoid-midterm-project --limit 500 --json nameWithOwner --jq '.[].nameWithOwner' | xargs -n 1 gh repo clone`

# 실행

```
cd ~/colcon_ws
colcon build
```

순서대로 실행

```
cd ~/colcon_ws
source ~/colcon_ws/install/setup.bash
ros2 launch dynamixel_hardware_interface dynamixel_hardware.launch.py
```

```
cd ~/colcon_ws
source ~/colcon_ws/install/setup.bash
ros2 run ik_walk ik_walk
```

```
cd ~/colcon_ws
source ~/colcon_ws/install/setup.bash
ros2 run tune_walk tune_walk
```
