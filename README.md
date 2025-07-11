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

| Variable    | Description                                                                                 |
|--------------|--------------------------------------------------------------------------------------------|
| `m_sf`   | Gravity compensation scale factor (1.0 = 100%, 0.4 = 40% default)                              |
| `acc_limit`    | Set joint acceleration limit (deg/s²), default = 3600                                    |
| `vel_limit`    | Set joint velocity limit (deg/s), default = [180, 180, 180, 180, 330, 330, 330]          |

---

## Function Descriptions

```c++
calc_torque_for_limit_avoid();
    # Applies torque to keep joints within the defined range
    # Automatically adds torque if joint exceeds its range

---