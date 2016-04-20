.. index:: hardware

.. _hardware:

Hardware Guide
--------------

The SiliconLab Sensor Node is provided with several sensor:

- Si114x: The monolithic Si114x sensors integrate multiple photodiodes, an analog-to-digital converter, a signal processor, up to 3-LED drivers and a digital I2C control interface. In this device are read proximity, ambient light and temperature.
- Si7021: The Si7021 I2C Humidity and Temperature Sensor is a monolithic CMOS IC integrating humidity and temperature sensor elements, an analog-to-digital converter, signal processing, calibration data, and an I2C Interface.
- MPU-9250: MPU-9250 is a multi-chip module (MCM) consisting of two dies integrated into a single QFN package. One die houses the 3-Axis gyroscope and the 3-Axis accelerometer. The other die houses the AK8963 3-Axis magnetometer er from Asahi Kasei Microdevices Corporation. Hence, the MPU-9250 is a 9-axis MotionTracking device that combines a 3-axis gyroscope, 3-axis accelerometer, 3-axis magnetometer and a Digital Motion Proc essorTM (DMP) all in a small 3x3x1mm package available as a pin-compatible upgrade 2 from the MPU-6515.
- Magnetometer is initialized wrongly if the voltage is lesser than 2.4V.

The **BGM111** uses I2C interface to communicate with sensors.

Datasheet and more
******************

Please refer to `architechboards <http://architechboards.org/>`_ website.

.. image:: _static/logo_architech.jpg

