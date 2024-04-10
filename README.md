# Suzuki-Swift-Sport-ZC31S-CAN-ReverseEngineering
This is a basic Flask app I wrote as a proof of concept to control my cars door locks. 


## CAN message documentation
Most messages with the same arbitration ID can be used in conjunction with each other. For example 3D8#000501 is the same as 3D8#000500 but flashes the hazards once.

### Arbitration ID 0x3D8 - BCM Door Lock Control
3D8#000500 - All Doors lock - Send once to toggle dome light

3D8#000100 - All Doors unlock

3D8#000200 - Driver door unlock

3D8#000501 - Door Lock with single hazards

3D8#000202 - Door unlock with double hazards

3D8#000020 - Start interior buzzer

3D8#000000 - Stop interior buzzer

3D8#000001 - Flash hazards once (Body control module uses this during lock)

3D8#000002 - Flash hazards twice (Body control module uses this during unlock)

### Arbitration ID 0x3D1 - BCM Door State

Good idea to send each command twice to wake CAN in case of ignition off.
