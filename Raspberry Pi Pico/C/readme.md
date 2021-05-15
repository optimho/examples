# How to program a Raspberry Pico in Linux

## In Linux
### Get the SDK and the examples
```
mkdir picoC
cd picoC

git clone -b master https://github.com/raspberrypi/pico-sdk.git
cd pico-sdk
git submodule update --init
cd ..
git clone -b master https://github.com/raspberrypi/pico-examples.git
```
### Get the compilers etc
```
sudo apt update
sudo apt install gcc-arm-none-eabi libnewlib-arm-none-eabi build-essential libssl-dev tk tkinter python3-tk
```

### Build CMake from source
The version of CMake that comes with Ubuntu 18.04 LTS needs to be updated to meet the minimum requirements of the Pico build system.

```
wget https://github.com/Kitware/CMake/releases/download/v3.19.4/cmake-3.19.4.tar.gz
tar -zxvf cmake-3.19.4.tar.gz
cd cmake-3.19.4/
./bootstrap
make
sudo make install
```

### Get the Pico Project Generator

```
git clone https://github.com/raspberrypi/pico-project-generator.git
```

### Generate your project


```
cd pico-project-generator
export PICO_SDK_PATH='/home/michael/picoC/pico-sdk'
./pico_project.py --gui
   tio /dev/ttyACM0```

### Build the project
First go into the project directory
```
cd ..
cd PROJECT (i.e cd ~/picoC/helloWorldC)
```
Edit the code, replace the puts() with:
```
        while (true) {
            printf("Hello from Pico!\n");
            sleep_ms(1000);
         }
```
And build
```
cd build
cmake ~/picoC/helloWorldC.c or cmake ..
make
```

### Copy .uf2 file to Pico

Press and hold the BOOTSEL button while powering on (or resetting) the Pico. A drive will appear called RPI-RP2. Copy the .uf2 directly to that drive. The Pico will reboot and start running the code.

# Use a terminal to monitor data from the Pico

dmesg |grep tty
look for ttyACM0

if it is ther you are good to go.
I have Tio emulator installed, to use this light weight emulator, just.
   tio /dev/ttyACM0
   ctrl -t q (the control and the t buttons followed by the q - Its a bit fiddely so persist)
   
```
And Switch to clion
```   
I have Clion configured to work with the Raspberry Pico.
Open Clion
Open the project folder ~/picoC/helloWorldC
Select okay for the defaults 

the project will open, now run the project and  select the terminal tab and then run tio /dev/ttyACM0
that should work as did the previous example.

You should be able to make changes and run the code, this should make the file.
I still had to put the Pico into the boot state and copy the .uf2 file to the Pico

I found the name of the pico when it is plugged into the computer holding down the reset button, it acts like a usb stick then.
copy the .uf2 file, example:
 cp helloWorldC.uf2 /media/michael/RPI-RP2
 



