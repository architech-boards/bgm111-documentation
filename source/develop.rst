.. index:: development

.. _develop:

Developing guide
----------------

This page explains how to develop under *Windows* with the **BG Tool** showing where to download, install and use it. To program the BGM111 is necessary not only the SiliconLab Sensor Node itself but also the board named **SLWSTK6201A**.

Installing
**********

The software could be downloaded from the `SiliconLabs website <https://www.silabs.com/products/wireless/bluetooth/Pages/bluetooth-smart-software.aspx>`_ the version used in this guide is `v0.9.2-446 <https://www.silabs.com/Support%20Documents/RegisteredDocs/bgm-0.9.2-446.exe>`_. In the silabs webpage you can find under the *download now* documents about BGScript, BGAPI, and example applications.
Once it downloaded install following default options.

SLWSTK6201A board
*****************

.. image:: _static/board_EZR32LG.jpg

The board `EZR32 Leopard Gecko Starter Kit <https://www.silabs.com/products/wireless/wirelessmcu/Pages/ezr32lg-starter-kits.aspx>`_ is needed to program the firmware in the **SiliconLab Sensor Node**. It is used as a J-Link. Without this hardware is not possible to flash the BGM111. It is necessary also make connections from the connector of the board with the device. To make this connection please follow this scheme:

.. image:: _static/board_bottom.jpg

As in figure:

==  ============
PT  Significance
==  ============
18  VCC
19  GND
11  RESET
7   SWDIO
8   SWCLK
==  ============

Connect these lines to the **SLWSTK6201A** board:

===========  ===========  ============
Sensor Node  SLWSTK6201A  Line
===========  ===========  ============
TP18	     P5 pin 40    VCC
TP19	     P5 pin 39    GND
TP11	     P5 pin 23    RESET
TP7          P5 pin 28    SWDIO
TP8          P5 pin 27    SWCLK
===========  ===========  ============

Before to continue, connect the **SiliconLab Sensor Node** to the **SLWSTK6201A** and connect the PC via USB to the **SLWSTK6201A**. Windows will install a virtual COM when recognizes the board.

The Project
***********

The project is developed with the **BGScript**. This language is compiled by **BGTool** and interpreted by **BGM111**. To know details about this programming language we suggest to read the specific document `Bluetooth Smart BGScript Developer Guide <http://www.hmangas.com/Electronica/Datasheets/Bluetooth%20Module/BLE112/Bluetooth+Smart+BGScript+Developer+Guide.pdf>`_ and read about the API functions with the document `BGM API Reference Guide <https://www.silabs.com/Support%20Documents/RegisteredDocs/BGM111-API-RM.pdf>`_.
Summarizing the BGScript is a simple event-driven BASIC-like application scripting language. It abstracts away the complexity of Bluetooth development, embedded programming and hardware interfaces. This kind of design enables fast, simple firmware development into BGM111 module. Obviously, it is not needed external MCU.

The BGScript project include several files:

- bgm111demo.bgproj: index file project, it is written all the files included in the project. The **BGTool** uses this file to open the project.
- hardware.xml: definitions of the hardware configuration, UART settings, GPIO uses,...
- gatt.xml: gatt specification used by the bluetooth pheriperal.
- bgm111demo.bgs: main source code, entry point of the firmare.
- peripheral.bgs: source code to comunicate with the sensors by I2C.

Now, to compile the project first up, download from `architechboards website <http://architechboards.org/>`_ the source code of the project. Extract it and launch **BGTool**. Select the COM connected to the **SLWSTK6201A** board.

.. image:: _static/bgt_com.jpg

After that, go to the menu clicking on *View->Upload Tool*.

.. image:: _static/bgt_view.jpg

Will appear a new window where to open the project file.

.. image:: _static/bgt_project.jpg
 
Before to build the project select where put the binary file, this file will be uploaded into the **BGM111**.
The last step is flash the firmware, to do this verify that all the connections are steady and click on *Upload* button. In few seconds the board will be programmed. Reset the device in order to run the new firmware uploaded.

