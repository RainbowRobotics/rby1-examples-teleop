# rby1-examples-teleop
Repo for Rainbow Robotics Master Arms


### Prerequisites

#### rby1-sdk


### Build From Source

```bash
git@github.com:RainbowRobotics/rby1-examples-teleop.git
git submodule update --init
```

```bash
cd rby1-examples-teleop
mkdir build
cd build
cmake -D CMAKE_BUILD_TYPE=Release ..
cmake --build .
```

```bash
./build/cpp/backback-style ...
```