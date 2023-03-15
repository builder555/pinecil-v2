[![Hits](https://hits.seeyoufarm.com/api/count/incr/badge.svg?url=https%3A%2F%2Fgithub.com%2Fbuilder555%2FPineSAM&count_bg=%23FF00BF&title_bg=%23625E5E&icon=pre-commit.svg&icon_color=%23E7E7E7&title=hits&edge_flat=false)](https://github.com/builder555/PineSAM/wiki)
![contributors welcome](https://custom-icon-badges.demolab.com/badge/contributors-welcome-A017A5.svg?logo=star&logoColor=white)
[![Download (all releases)](https://img.shields.io/github/downloads/builder555/pinesam/total?color=A017A5)](https://github.com/builder555/PineSAM/releases/)
[![Latest release](https://img.shields.io/github/v/release/builder555/pinesam?color=7700b3)](https://github.com/builder555/PineSAM/releases/latest)
![bluetooth](https://custom-icon-badges.demolab.com/badge/-bluetooth-7700b3.svg?logo=bluetooth&logoColor=white)
<br><br>
<img src="./images/PineSAM_logo-A017A5.png" align="left" width="150" height="48" style="float:left"> <br clear="left" />
---
<br>
<img src="./images/workHUD.png" align="right" width="350" style="float:left">

#### PineSAM = Pinecil Settings and Menus

Why focus on soldering when you can play with the settings instead? With this app you have full control over your new shiny Pinecil V2 from your computer using bluetooth.

**NB**: No special browser BLE GATT or flags required and works on all major OS/devices.

**NB**: This app needs the python backend to run on a computer, it CANNOT run entirely in the browser like Joric's UI.

<details>
  <summary>Full settings view</summary>
  <p>
    <img src="./full_settings.png"/>
  </p>
</details>
<div style="clear:both;">&nbsp;</div>
<br clear="right"/>

# 💫 Features

- [x] Automatically detect Pinecil V2 over BLE bluetooth.
- [x] Get all settings from V2.
- [X] Show hints toggle button for help messsages.
- [X] Modify settings and validate values before sending to V2.
- [X] Save to flash toggle button to commit setting changes directly to V2 (leave off for Work view to save flash cycles).
- [X] Work View main screen with: Set °C/°F `[+][-]` buttons, live tip °C/°F updates, peak watts, live watts, input voltage.
- [X] Custom Preset buttons to allow quick change of user defined temperatures (PineSAM extra feature not available directly inside Pinecil).
- [X] Backend runs locally on all major platforms/OS while the User Interface runs on your favorite browser.
- [X] Temperature automatically adjusts based on °C or °F setting.
- [X] Power Settings: hide minimum voltage (per cell) when power source is not 3S-6S.

## Platforms
 | System  | MacOS | Linux | Windows | iOS | Android|
 | :-----: | :-----: | :---: | :---: | :-: | :----: |
 | UI      |:heavy_check_mark:|:heavy_check_mark:|:heavy_check_mark:|:heavy_check_mark:|:heavy_check_mark:|
 | backend |:heavy_check_mark:|:heavy_check_mark:|:heavy_check_mark:|
<br>

# :desktop_computer: Install Options

## I. Using pre-made binaries

1. Does not require installation of python or node.js
2. Download latest [release](https://github.com/builder555/PineSAM/releases/latest) version for your OS system (Mac, Linux, Windows).
3. **Mac/Linux**: extract and run `./start.sh` in terminal.
4. **Windows**: 
   * right click on the zip, properties> general, check box to Unblock, then extract.
   * Run powershell as admin, cd to the pinesam folder and `.\start.ps1`
   * Allow any windows pop-up warnings about "serve.exe" and "main_sever.exe".
   * If you get errors in powershell, set the permissions to RemoteSigned to allow scripts ([reference](https://lazyadmin.nl/powershell/running-scripts-is-disabled-on-this-system/)).
   * ```Set-ExecutionPolicy RemoteSigned```

## II. Install the Dev version (Source-all-xxx)
### Requirements 
- any browser to run the UI (IE is not a browser)

For the backend script, install:
- [python 3](https://www.python.org/downloads/) (tested with 3.10/3.11)
- pipenv
- [node+npm](https://nodejs.org/en/download/)

<details>
  <summary> Mac/Linux dev install</summary>
  <p>
    
#### Setup

```shell
git clone https://github.com/builder555/PineSAM
cd PineSAM
chmod +x setup-dev.sh
chmod +x run-dev.sh
./setup-dev.sh
```

#### Run
```shell
./run-dev.sh
# press CTRL+C in the terminal window to stop
```
* On a Mac http://localhost:8080 will open in your browser automatically.
* Some Linux distros may need http://localhost:8080 opened manually. Debian12 hints [here](https://github.com/builder555/PineSAM/discussions/47#discussion-4884758).

  </p>
</details>
<div style="clear:both;">&nbsp;</div>

<details>
  <summary>Windows dev install</summary>
  <p>

#### Install
If you already have Python and NodeJS installed, you can skip to step 3.

1. Install Python: https://www.python.org/downloads
    * Check "Add python.exe to PATH" and select "Customize Installation"
    * Check "Add Python to environment variables" option
    * See a reference screen [here](https://github.com/builder555/PineSAM/discussions/7#discussion-4862766).
2. Install NodeJS: https://nodejs.org/en/download/
3. Download the Source-all-xxx from the latest release: https://github.com/builder555/PineSAM/releases/latest
4. Right click the zip and open Properties > General tab and check _Unblock_ if it appears at the bottom. Then Unzip it.
5. Run powershell as administrator, set permissions to RemoteSigned ([reference](https://lazyadmin.nl/powershell/running-scripts-is-disabled-on-this-system/)).
```shell
# setting this one time in powershell normally persists on reboots.
Set-ExecutionPolicy RemoteSigned
```
#### Run
1. Change directory, `cd` to the location of the PineSAM folder that was unzipped above.
```shell
setup-dev.bat   # only need to run this one time for each new version
run-dev.bat     # run this command every time you use Pinecil
```
  </p>
</details>
<div style="clear:both;">&nbsp;</div>

## :signal_strength: Remote access

You can access the settings remotely (i.e, from a phone) once the app is running on the main PC/laptop.

* Find the [local IP address](https://lifehacker.com/how-to-find-your-local-and-external-ip-address-5833108) of the device running the app.
* open `http://<ip-address>:8080/` on the second device on the same network (i.e. phone).
* this works to run PineSAM on an iPhone or Android if you don't want to install python on the phone.
* Pinecil needs to be within BLE range of the computer running the PineSAM app; the 2nd device/phone just needs to be within Wifi/network range of the main computer.

## 👀 Known issues
1. bleak causes Python to crash on Mac: https://github.com/hbldh/bleak/issues/768
    * possible solution: give access to iTerm (or whichever terminal you use) to Bluetooth in Settings
2. Pinecil not detected
    * possible solution: you paired your Pinecil using system settings - unpair it from all other places.
    * possible solution: need to [flash](https://github.com/Ralim/IronOS/discussions/1518#discussioncomment-4866637) [BLE firmware](https://github.com/builder555/PineSAM/files/10797411/Pinecilv2_EN.zip)
    * upcoming Ralim's IronOS 2.21 will be the first stable release that has BLE support built-in for V2. Before 2.21, only beta BLE versions of IronOS firmware will work.
    
3. Windows Powershell permissions issue
    * windows by default does not allow any scripts to run in powershell. Make sure the zip file property is _Unblock_ and set powershell to remotesigned ([reference](https://lazyadmin.nl/powershell/running-scripts-is-disabled-on-this-system/)):<br>
    `set-executionpolicy remotesigned`
    * check that windows has not reset the permissions in powershell with `Get-ExecutionPolicy` and change it back to `RemoteSigned`.
4. See the [Discussions](https://github.com/builder555/PineSAM/discussions) section for install tips and solutions to some common issues.


## 🔍 Testing

```shell
# run inside 'backend' directory:
pipenv run test
```
## 💬 Questions?
Feel free to [open an issue](https://github.com/builder555/PineSAM/issues).

## :heart_eyes: Support
If you like this project, give it a ⭐ and share it with friends!


## :book: References

- [Pinecil](https://wiki.pine64.org/wiki/Pinecil) - The Pinecil Wiki page
- [IronOS](https://github.com/Ralim/IronOS) - The OS running on this soldering iron
- [Pinecil Web UI](https://github.com/joric/pinecil) - A neat web-based UI, requires bluetooth browser support
- [Pinecil Authenticity Checker](https://pinecil.pine64.org/) - almost all AliExpress Pinecils are fake, check your V2!


