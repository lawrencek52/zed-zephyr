.. _zed_sensor1:

Zed-Boards Sensor1 Shield
######################

Overview
********

The `Zed-Boards Sensor1 I2C to Motion Sensors Adapter Shield`_ features
a `Bosch BMI270 accelerometer gyro`_ 

.. figure:: zed_boards_sensor1.webp
   :align: center
   :alt: Zed Boards Sensor1 Shield

   Zed Boards Sensor1 Shield (Credit: Zed Boards)


Requirements
************

This shield can be used with Zed Boards CPU1 CON2 which
   provides I2C, UART, and GPIO
The target board must define a ``i2c1`` and ``uart1`` node labels.
See :ref:`shields` for more details.


Pin Assignments
===============

+-----+------------+------------------------------------+
| Pin |     Signal | Function                           |
+=====+============+====================================+
|   4 |        SDA | Sensor1 I2C SDA                    |
+-----+------------+------------------------------------+
|   5 |        SCL | Sensor1 I2C SCL                    |
+-----+------------+------------------------------------+
|   6 |        TxD | serial data from GPS module        |
+-----+------------+------------------------------------+
|   7 |        RxD | serial data to GPS module          |
+-----+------------+------------------------------------+
|   8 |     nRESET | reset to GPS module and gpio       |
+-----+------------+------------------------------------+
|   9 | n_BCKP_RST | backup reset to GPS module         |
+-----+------------+------------------------------------+
|  10 |    LED_ENA | enable LEDs (or power save)        |
+-----+------------+------------------------------------+
|  11 |       1PPS | 1 pulse per second from GPS module |
+-----+------------+------------------------------------+
|  12 |     IO_IRQ | interrupt form houskeeping gpio    |
+-----+------------+------------------------------------+

See :dtcompatible:`bosch,bmi270` for documentation on how to adjust the
devicetree file for sleep mode etc.


Programming
***********

Set ``--shield zed_sensor1_con2`` when you invoke ``west build``. For example
when running the :zephyr:code-sample:`bmi270` accelerometer, gyro scanning sample:

.. zephyr-app-commands::
   :zephyr-app: samples/drivers/bmi270
   :board: zed_boards_cpu1_nrf5340
   :shield: zed_boards_sensor1_motion
   :goals: build

Connect the shoeld to CON2 with a flex cable before running the sample.

.. _Zed Boards Sensor1 I2C Motion Sensors Adapter Shield:
   ttps://learn.zed_boards.com/zed_boards-sensor1

.. _Bosch bmi270 accelerometer gyro:
   https://www.bosch-sensortec.com/media/boschsensortec/downloads/datasheets/bst-bmi270-ds000.pdf
