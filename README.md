# murasaki_test_install
Installer testing project. Dedicated to Murasaki developers. Not useful to the Murasaki application developer. 

# Coverage
Test the Murasaki/install script. To test, do followings : 
1. Generate the code from ioc file of the each directory. 
2. Run ./set_murasaki_develop script to update all murasaki library as the newest HEAD of the develop branch. 
3. Run the murasaki/install script and see the build sequence go without any problem. 
4. Run the program on the board. If the LED blinks, no problem. 

This test cannot cover HardFault handling. 

# Test target
Following is the list of the Target 

| Project         | CORE      | Board         |
|-----------------|-----------|-----------------|
| nucleo-F091-64  | CORTEX-M0 | [NUCLEO-F091RC](https://www.st.com/content/st_com/en/products/evaluation-tools/product-evaluation-tools/mcu-mpu-eval-tools/stm32-mcu-mpu-eval-tools/stm32-nucleo-boards/nucleo-f091rc.html) |
| nucleo-G070-64  | CORTEX-M0+| [NUCLEO-G070RB](https://www.st.com/content/st_com/en/products/evaluation-tools/product-evaluation-tools/mcu-mpu-eval-tools/stm32-mcu-mpu-eval-tools/stm32-nucleo-boards/nucleo-g070rb.html)|
| nucleo-F446-64  | CORTEX-M4 | [NUCLEO-F446RE](https://www.st.com/content/st_com/en/products/evaluation-tools/product-evaluation-tools/mcu-mpu-eval-tools/stm32-mcu-mpu-eval-tools/stm32-nucleo-boards/nucleo-f446re.html) |
| nucleo-G431-64  | CORTEX-M4 | [NUCLEO-G431RB](https://www.st.com/content/st_com/en/products/evaluation-tools/product-evaluation-tools/mcu-mpu-eval-tools/stm32-mcu-mpu-eval-tools/stm32-nucleo-boards/nucleo-g431rb.html)|
| nucleo-L152-64  | CORTEX-M3 | [NUCLEO-L152RE](https://www.st.com/content/st_com/en/products/evaluation-tools/product-evaluation-tools/mcu-mpu-eval-tools/stm32-mcu-mpu-eval-tools/stm32-nucleo-boards/nucleo-l152re.html) |
| nucleo-H503-64  | CORTEX-M33| [NUCLEO-H503RB](https://www.st.com/content/st_com/en/products/evaluation-tools/product-evaluation-tools/mcu-mpu-eval-tools/stm32-mcu-mpu-eval-tools/stm32-nucleo-boards/nucleo-h503rb.html)|
| nucleo-L412-64  | CORTEX-M4 | [NUCLEO-L412RB-P](https://www.st.com/content/st_com/en/products/evaluation-tools/product-evaluation-tools/mcu-mpu-eval-tools/stm32-mcu-mpu-eval-tools/stm32-nucleo-boards/nucleo-l152re.html) |
| nucleo-F722-144 | CORTEX-M7 | [NUCLEO-F722ZE](https://www.st.com/content/st_com/en/products/evaluation-tools/product-evaluation-tools/mcu-mpu-eval-tools/stm32-mcu-mpu-eval-tools/stm32-nucleo-boards/nucleo-f722ze.html) |
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
 
     

# Environment
These projects are tested with environment below
 - [Ubuntu](https://ubuntu.com/) 22.04 LTS
 - [STM32CubeIDE](https://www.st.com/ja/development-tools/stm32cubeide.html) 1.12.0
 - [Murasaki](https://github.com/suikan4github/murasaki) 4.0.0

# License
This project is distributed under [MIT License](LICENSE)