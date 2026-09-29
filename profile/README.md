# gh auth login 설정 필요

`git clone -b jazzy https://github.com/ROBOTIS-GIT/DynamixelSDK.git`

`git clone -b jazzy https://github.com/ROBOTIS-GIT/dynamixel_interfaces.git`


`gh repo list Robit-humanoid-midterm-project --limit 500 --json nameWithOwner --jq '.[].nameWithOwner' | xargs -n 1 gh repo clone`
