# Shelly-Pro-EM-50-Integration-with-Venus-OS
Enables an inexpensive single-phase, dual channel Shelly energy meter to work as a grid and inverter meter.

This project was created 2 years ago when I discovered the Pro EM-50. It is still working in Venus 3.70. It is a modification of Shelly 3EM code written by others. It uses the Shelly's Outbound Websocket service and Venus Ethernet port. Implementation is done by adding these modified files.
Here are the steps I use to implement using Ethernet:



Basic Shelly Setup:

Follow Shelly install directions. Install an Ethernet cable between devices.

Channel 0 current coil is attached to grid HOT wire

Channel 1 current coil is attached to HOT output of inverter or generator

Log into the device and go to the ‘Settings’ – ‘Connectivity settings’ – ‘Outbound websocket’

Connection type  Default TLS   Server  ws://169.254.1.2:8000

Go to ‘Settings’  ‘Network setting’  Ethernet  Check ‘Enable’ and ‘Set static IP address’ 

IP address: 169.254.1.3 Network Mask: 255.255.255.0 Gateway: 169.254.1.1 DNS: 169.254.1.1



Venus OS Setup:

‘Settings’ ‘Ethernet’ ‘IP configuration’ ‘manual’  IP address: 169.254.1.2 Netmask: 255.255.255.0 Gateway: 169.254.1.1

Go to /opt/victronenergy/dbus-shelly and rename dbus_shelly.py to dbus_shelly.py.org and meter.py to meter.py.org

Import the modified .py files into this directory.

Ensure the file permissions of dbus_shelly.py match the original.

Note: I only modified GUIv1 pages to work with these mods. GUIv2 is not done.

Go to /opt/victronenergy/gui/qml and remane these files: 
PageAcInModel.qml to PageAcInModel.qml.org and DetailAcInput.qml to DetailAcInput.qml.org

Import the modified .qml files into this directory.


Reboot.


Disclaimer- I have very limited coding skills and very new to this platform. Welcome any advice for improvement.
