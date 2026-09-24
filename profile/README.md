# Tampere Formula Student Software Development Guidelines & Tools

## Version Control
- All new project repositories for the TFS27 should have their name start with the prefix ```TFS27```. For example: ```TFS27-CAN-Node```.
- The Master/main branch of a project should always include a "ready-to-drive" version of the software in that repository. Use separate development branches during development.
- Development branches should be named with a ```dev-``` prefix. For example: ```dev-read-adc```.
- All repositories must include a ```README.md``` with a description of the software.
- All code changes should be committed to Git, even if the changes are "tunkkausta". Use *descriptive* commit messages.
        Example commit message: "dev-apiReformat: Added new paths to router"
- Make sure your .gitignore file is in order to not push anything extra to the repositories!
- Don't leak .env files with sensitive info! Backup to OneDrive and encrypt it if necessary.
- INCLUDE BUILDING AND RUNNING INSTRUCTIONS

### [Further reading and basics of version control](https://tuni.sharepoint.com/:w:/r/sites/TG-tampereuasmotorsport/Jaetut%20asiakirjat/Dept.%20Electrics%20and%20Embedded%20Systems/TFS27/Embedded%20systems/Coding%20rules%20of%20engangement.docx?d=w850cf0e830dd4c9fa19bfd258565cf98&csf=1&web=1&e=eHzX61)

## Embedded Firmware Development Environment Setup

### Windows
#### 1. Install [Visual Studio Code](https://code.visualstudio.com/sha/download?build=stable&os=win32-x64-user).
Once installed, install the following extensions:
- ```STM32CubeIDE for Visual Studio Code```
- ```CMake Tools```
- ```C/C++ Extension Pack```

#### 2. Install [STM32CubeMX](https://www.st.com/cloudfront/publish/stm32cubemx-win-v6-18-1/6.18.1/en/SetupSTM32CubeMX-6.18.1-Win-x86_64.zip?Expires=1790273435&Signature=WgbzfcIwdn0dsPMACyo3QYAJ3swFjcp5Gs9VHxXj8eg28wlbwGi~tO4nIkzhIOx5AAodxA~lRkNfrYBVV3YWCEEo2nQ3xm4s7Twe9ZHOV7H1WnQHsWe4A8rFB8BXu8A~L7JeZCSwTYBPhmj31dvxwrQx9U-Esol4SuCqNIGU87aj4dbSuo7W8mU7vVN1pRcksjoc-gPSMrhUNPY13Y47F~ly2mdda3dje7O2DlU696CfxtEXI~sdAcUpo1vc1g8JJ6xggfrOomjxJ3I6HlhK5FovSpKx1fKUFau-8ffUz~oxFKTn-14bLpXyoz2AcO8lTn4hIMelC8CYa9AJiXoWMQ__&Key-Pair-Id=K27828FUHOZJS8) and [STM32CubeProgrammer](https://www.st.com/cloudfront/publish/stm32cubeprg-win64-v2-23-0/2.23.0/en/SetupSTM32CubeProgrammer_win64.zip?Expires=1790273585&Signature=L5rNtcHHn~dh-S0SUZkv8TNDjgWo12aJdbQqVt9j-pha58GOvjlJnzGLL~qjOB6S2JVvobaz~Rk676wlmq3hZxeXkSnFj4g5cFrTC9c8TlBhxkJi-g~HDTFiKYAbFPYNQEvPLvfsieZ9lUPUHDdyDRgMnZ~DY6tNC2ukDRaSI5SNYpkbXP60nlYzaE7A7PeO1HSjTbEHh8bU8rYu8OXhpSCRbTZdjxOGXdl94zZZ3SkGhG3hVpTwTVwtjA-CY6EbEwO2EkjlqK1eHznfHNdEYAP1kFsu-PBDRuV6stFk3GDUzCXOv0JLKZr8gG953VN5s75P65No2IjQ2Do7xb6Kfw__&Key-Pair-Id=K27828FUHOZJS8).

#### 3. Install Ninja and CMake:
Paste the following into Command Prompt:
```
winget install -e --id Ninja-build.Ninja
```
```
winget install -e --id Kitware.CMake
```
#### 4. Install the [MinGW-w64 toolchain](https://github.com/msys2/msys2-installer/releases/download/2025-08-30/msys2-x86_64-20250830.exe).
Once installed, a terminal window will open. Paste the following into it:
```
pacman -S --needed base-devel mingw-w64-ucrt-x86_64-toolchain
```
Accept the default number of packages in the toolchain group by pressing ```Enter```.

Enter ```Y``` when prompted whether to proceed with the installation.

Add the path of your ucrt64 `bin` folder to the Windows `PATH` environment variable by using the following steps:
   1. In the Windows search bar, type **Settings** to open your Windows Settings.
   1. Search for **Edit environment variables for your account**.
   1. In your **User variables**, select the `Path` variable and then select **Edit**.
   1. Select **New** and add the MinGW-w64 destination folder you recorded during the installation process to the list. If you used the default settings above, then this will be the path: `C:\msys64\ucrt64\bin`.
   1. Select **OK**, and then select **OK** again in the **Environment Variables** window to update the `PATH` environment variable.
      You have to reopen any console windows for the updated `PATH` environment variable to be available.

#### 5. Create a new project in STM32CubeMX:
- Click on ```ACCESS TO MCU SELECTOR```.
- Select an MCU and click on ```Start Project```.
- Use the ```Pinout & Configuration``` and ```Clock Configuration``` tabs to configure the MCU.
- In the ```Project Manager``` tab, give your project a name and change ```Toolchain / IDE``` to **CMake**.
- Click on ```GENERATE CODE```.

#### 6. Setup VSCode
- Open the generated project folder in VSCode.
- The following popup should appear, click `Yes`.

<img width="447" height="84" alt="image" src="https://github.com/user-attachments/assets/8edf6a68-178d-48d8-8523-40a79b872254" />

- Navigate to the CMake extension and click on ```Configure```. Select **Debug**.
- You should now be able to build the binary. Click on the ```Build``` button on the bottom left of the window.

### Linux
to be continued
