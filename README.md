# Introduction
## Devices
1. [PLC](#1): Siemens S7-1200 CPU 1211C DC/DC/DC
2. [RS232/485/422 to TCP/IP converter](#2): ZLAN 5207M
3. [Pump Controller](#3): Kamoer Modbus-RTU
4. Pump: Kamoer KHL-SZ-S35
5. Others: CAT5 Network Cable *1, Power Supply *1

<h2> Network View </h2>
<div align=center>
    <img src="/../shots/DeviceMap.png" height="500px"/>
</div>

<h2 id="1"> PLC Configuration </h2>

- TIA Portal Version: V18
- External Library: LGF_CalcCRC16, LGF_Impulse
- Add-Ins: Siemens.ExportImportV18.addin

<h2 id="2"> Converter Configuration </h2>

- Convert Protocol: TCP Server

<h2 id="3"> Pump Controller Configuration </h2>

- SW1-SW12: 000001***011
> Notice: The CRC16 checksum code accepted by the controller, with high and low byte order reversed from the Portal's built-in Modbus sender program (i.e., big-endian and little-endian problem).

<br/>

# How to use
1. Extract and copy the [Siemens.ExportImportV18.addin](https://support.industry.siemens.com/cs/attachments/109773999/109773999_TIAV18_Add-In_Export_Import_v100_App.zip) into the "AddIns" folder of your TIA Portal installation path. Per default, it is C:\Program Files\Siemens\Automation\Portal V18\AddIns\ .
2. Opening TIA Portal V18.
3. Add a PLC in "Device and network".
4. In "Add-Ins" panel, active the Siemens.ExportImportV18.addin.
5. Right click the program block, select "Export/Import-Import from directory" and choose the .xml-file directory.
6. Refresh and reconnect the FB or FC blocks.