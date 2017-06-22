# Redundant_Sensing

Redundant sensing on BACnet FP (router). This is the code on BACnet router who forwards commands from the workstation to physical devices (also bacnet devices). It reflects object names on physical devices on the FP. It works for any commands (read/write). It should run as .bacserv

AV#1 on physical devices is reflected as AV#1 here.

The router automatically find PD with BACnet device ID 123 and forwards the request to PD.

PD address is manually set up in src-> rp.c ->forward_rp_req-> device_id.

Note that all devices have to be within the same subnet.

# How to run the code 

ReadProp $ demo/readprop/bacrp

bacrp device-instance object-type object-instance property [index]

./bin/bacrp 1234 1 0 85

WriteProp $ demo/writeprop/bacwp

bacwp device-instance object-type object-instance property priority index tag value [tag value...]

./bin/bacwp 1234 1 0 85 16 -1 4 100

(Note: object #1 is for analog output objects)
