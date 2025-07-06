# rby1-examples-teleop
Repo for Rainbow Robotics Master Arms




# Get Started Teleoperation Example


#### Example Descriptions

| Example      | Description                                                                                 |
|--------------|---------------------------------------------------------------------------------------------|
| `backpack-B` | Wearable-type configuration with a basic handle                                             |
| `stand-B`    | Stand-type configuration with a basic handle                                                |
| `stand-P`    | Stand-type configuration with a Pinch handle                                                |

---

### Prerequisites

#### rby1-sdk


### Build From Source

```bash
git clone --recurse-submodules https://github.com/RainbowRobotics/rby1-sdk.git
cd rby1-sdk
sudo cmake --build --target install --preset conan-release
#install rby1-sdk in system folder
```

```bash
git clone --recurse-submodules https://github.com/RainbowRobotics/rby1-examples-teleop.git
cd rby1-examples-teleop
mkdir build
cd build
cmake -D CMAKE_BUILD_TYPE=Release ..
cmake --build .
```


## C++ Example

```c++
./build/cpp/stand-P <server address> <servo> <mode>

      # example
      # ./build/cpp/stand-P 192.168.30.1:50051 impedance
      
```

#### Option Descriptions

| Option             | Description                                                                 |
|--------------------|-----------------------------------------------------------------------------|
| `<server address>` | IP address of the Robot PC                                                  |
| `<servo>`          | Select the servo to turn on (default = all, except 'head')                  |
| `<mode>`           | Control mode: choose either `position` (default) or `impedance`             |


---

## Variable Descriptions

```c++
double m_sf = 0.4;
    # Gravity compensation scale factor
    # 1.0 = 100% compensation
    # 0.4 = 40% compensation (default)

calc_torque_for_limit_avoid();
    # Applies torque to keep joints within the defined range
    # Automatically adds torque if joint exceeds its range

acc_limit();
    # Joint acceleration limit (deg/s²)
    # Default: 3600 for all joints

vel_limit();
    # Joint velocity limit per joint (deg/s)
    # Default: [180, 180, 180, 180, 330, 330, 330]
```
