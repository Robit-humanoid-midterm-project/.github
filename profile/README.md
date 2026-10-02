# gh auth login 설정 필요

ws 내 src로 이동 후

```
git clone -b jazzy https://github.com/ROBOTIS-GIT/DynamixelSDK.git
git clone -b jazzy https://github.com/ROBOTIS-GIT/dynamixel_interfaces.git

gh repo list Robit-humanoid-midterm-project --limit 500 --json nameWithOwner --jq '.[].nameWithOwner' | xargs -n 1 gh repo clone
```

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

# alias 단축어

cd ~/colcon_ws<br>
source ~/colcon_ws/install/setup.bash<br>
모두 alias로 설정되어 있음 따로 명령할 필요 없음<br>

dynamixel_hardware_interface 실행
```
dy
```

ik_walk 실행
```
ik
```

tune_walk 실행
```
tu
```

ebimu 실행
```
imu
```

# 모든 repo fetch

ws 내 src로 이동 후

```
for d in */; do
  if [ -d "$d/.git" ]; then
    echo "=== Fetching: $d ==="
    (cd "$d" && git fetch --all)
  fi
done
```

# 추가된 repo만 clone

ws 내 src로 이동 후

```
gh repo list Robit-humanoid-midterm-project --limit 500 --json name --jq '.[].name' | while read -r repo; do
  if [ ! -d "$repo" ]; then
    echo "=== 새로 추가된 레포 클론 중: $repo ==="
    gh repo clone "Robit-humanoid-midterm-project/$repo"
  else
    echo "=== 이미 존재함 (스킵): $repo ==="
  fi
done
```
