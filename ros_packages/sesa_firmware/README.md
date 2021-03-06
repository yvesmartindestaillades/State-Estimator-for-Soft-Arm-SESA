# About
This package compiles the Arduino code using the Aruidno IDE kernel and loads it to an Arduino Mega 2560. The package use the generate_arduino_firmware() function from the rosserial_arduino package. A tutorial can be found here: http://wiki.ros.org/rosserial_arduino/Tutorials/CMake

Some constants are based on my custom electronic schematics. Please check the electronics shematics below to use correctly the code.

# Different firmwares
This project has 2 possible firmwares:
    - *stream*, the plug and play firmware. This firmare streams the IMU data. 
        The IMU is set in NDOF mode, which auto-calibrate across time using the embedded firmware of BNO055 (Fast Magnetometer calibration).
        If the parameter `calib/use_saved`  is true, the firmware loads a pre-recorded calibration `calib/saved_file` saved in `calib/saved_path`.
<<<<<<< HEAD

    - *calibration*. This firmware streams the calibration state. This ROS package can save the stream calibration data into a local file throught the `save_calibration.py` script.
=======
    - *calibrate*. This firmware streams the calibration state. This ROS package can save the stream calibration data into a local file throught the `save_calibration.py` script.
>>>>>>> 6e4d26a74b540ca2ac7646d27e3cf20a40f01e2a

# How to compile and load the firmware to Arduino

To compile the firmware for *stream*, open a terminal and enter the following commands:
```
$ cd PATH_TO/catkin_ws
$ catkin_make sesa_firmware_arduino_stream-upload
```
To compile and load the firmware for *calibration*, enter the following commands:
```
$ cd PATH_TO/catkin_ws
$ catkin_make sesa_firmware_arduino_calibrate-upload
```

# Electronics schematics
![Elec](/images/elec_sketch.png)
