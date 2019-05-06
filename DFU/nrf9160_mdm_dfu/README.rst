How to install:
1. Extract the content of this zip file to a location of your choosing.
2. If you do not have a version of python 3 installed, install python 3.6 or newer. Can be found here: https://www.python.org/downloads/
3. a) In comand prompt, run: pip install nrf9160_mdm_dfu-0.10.1+dev-py3-none-any.whl
3. b) If you have python 2 installed, pip might be linked to this instead of your python 3 distribution, you can then run *path to your python 3 installation* -m pip install nrf9160_mdm_dfu-0.10.1+dev-py3-none-any.whl

How to use:
To use this tool, you need to have the following three files:
    ZZzzZZzz.ipc_dfu.signed.ihex    
    firmware.update.image.hex
    firmware.update.image.digest.txt

Where ZZzzZZzz is a part of the digest of your current modem firmware.

Open a command prompt in the folder where your previously mentioned files are located, and run nrf9160_mdm_dfu --update  

Alternatively, one can point to the specific files using the following commands in combination  with --update 
--fwpath path
--ipcpath path
--fwdigestpath path

If you have multiple nrf9160 devices connected to the computer at the same time, you can specify which kit to connect to using -s SNR / --snr SNR, where SNR is the serial number of the jlink debugger probe.

************************************************************************************************************
usage: nrf9160_mdm_dfu [-h]
                       (--update | --read Addr Len file | --UUID | --digest)
                       [-s SNR] [-q] [--fwpath path] [--ipcpath path]
                       [--fwdigestpath path]

Update the firmware of nrf9160 devices.

optional arguments:
  -h, --help            show this help message and exit
  --update              update firmware
  --read Addr Len file  Reading from the modem, Addr and Len must be hex
                        values, file is a file path
  --UUID                read UUID
  --digest              read digest from modem
  -s SNR, --snr SNR     Serialnumber for the nrf9160 device.
  -q, --quiet           Enables quiet mode.
  --fwpath path         firmware update image path
  --ipcpath path        IPC hex file path
  --fwdigestpath path   firmware update image digest path
  