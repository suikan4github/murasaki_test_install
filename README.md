# murasaki_test_install
Installer testing project. Dedicated to Murasaki developers. Not useful to the Murasaki application developer. 

# Coverage
Test the Murasaki/install script. 
Run the script and see the build sequence go without any problem. 

Run the program on the board. If the LED blinks, no problem. 

This test cannot cover HardFault handling. 

# Test target
Following is the list of the Target 

| Project         | CORE      | Board         |
|-----------------|-----------|-----------------|
| nucleo-f091-64  | CORTEX-M0 | [NUCLEO-F091RC](https://www.st.com/en/evaluation-tools/nucleo-f091rc.html) |
| nucleo-f446-64  | CORTEX-M4 | [NUCLEO-F446RE](https://www.st.com/content/st_com/en/products/evaluation-tools/product-evaluation-tools/mcu-mpu-eval-tools/stm32-mcu-mpu-eval-tools/stm32-nucleo-boards/nucleo-f446re.html) |
| nucleo-l152-64  | CORTEX-M3 | [NUCLEO-L152RE](https://www.st.com/ja/evaluation-tools/nucleo-l152re.html) |
| nucleo-l412-64  | CORTEX-M4 | [NUCLEO-L412RB-P](https://www.st.com/ja/evaluation-tools/nucleo-l152re.html) |
| nucleo-f722-144 | CORTEX-M7 | [NUCLEO-F722ZE](https://www.st.com/content/st_com/en/products/evaluation-tools/product-evaluation-tools/mcu-mpu-eval-tools/stm32-mcu-mpu-eval-tools/stm32-nucleo-boards/nucleo-f722ze.html) |
| nucleo-f746-144 | CORTEX-M7 | [NUCLEO-F746ZG](https://www.st.com/content/st_com/en/products/evaluation-tools/product-evaluation-tools/mcu-mpu-eval-tools/stm32-mcu-mpu-eval-tools/stm32-nucleo-boards/nucleo-f746zg.html) |
| nucleo-H743-144 | CORTEX-M7 | [NUCLEO-H743ZI](https://www.st.com/content/st_com/en/products/evaluation-tools/product-evaluation-tools/mcu-mpu-eval-tools/stm32-mcu-mpu-eval-tools/stm32-nucleo-boards/nucleo-h743zi.html) |



# Usage
Follow the procedure below. 
  1. Import all projects from your local repository by STM32CubeIDE.
  1. Create a temporary branch ( let's say "sandbox" ) based on the master branch. And then, checktout the sandbox. 
  1. Right-click the project and then, execute the "Generate Code" menu. To be sure, the code is possible to build. At this moment.
  1. Open a shell window and then, execute the following commands :
     1. cd project-directory
     1. cd Murasaki
     1. ./install
  1. From the STM32CubeIDE, open the project properties
     1. Goto "C/C++ General" -> "Paths and Symbols"
     1. Goto "Include" tab and then, select the "GNU C++" in the language. 
     1. Add "murasaki/Inc" 
     1. Goto "Source Location" tab. 
     1. Add "murasaki/Src" 
     
Note: The Nucleo 64 cause compile error by default because the difference of the UART connected to the serial port. 

| Board      | UART |
-------------|------
| Nucleo 144 | UART3 |
| Nucleo 64  | UART2 |

To correct this problem, fix followings :
- Fix the declaration of the hart3 to huart2 in Src/murasaki_platform.cpp
- Fix the creation of the debug UART referring huart3 to huaret2 in Src/murasaki_platform.cpp

# Environment
These projects are tested with environment below
 - [Ubuntu](https://ubuntu.com/) 16.04 LTS
 - [STM32CubeIDE](https://www.st.com/ja/development-tools/stm32cubeide.html)

# License
This project is distributed under [MIT License](LICENSE)