This document give a larger view of the expected hardware and software functions, along side with the experiments and research.


Radio3.network is a set of software and hardware for creating autonomous networks where people and device can connect to exchange data on their own.

At the moment it is heavily based on ESP32 and LoRa network because of the affordable price and long range communication range. In the end you can think about this as the walkie-talkie for data instead of voice.


A radio station/receiver that is free and provides the following features:

+ Email (internal, external)
+ Chat (with contact list)
+ Local Twitter
+ Forum
+ Blog
+ Radio
+ Telephone
+ Directory (people, places, orgs)
+ Sharing of files, images, and recordings
+ Map of relevant locations
+ Local news/events
+ Local market (where to buy vegetables, services, volunteering, etc.)
+ Local temperature/humidity
+ Make payments with cryptocurrencies (monero, beam tokens, LN)
+ Web pages with templates (to showcase local communities in the area)
  + Individual profile
  + House profile
  + Community/orgs profile
  + Include other contacts (phone, address, coordinates, etc.)
+ Library (books, manuals, movies by topics)


### Integrations:

+ Regular web (through radio3.network)
+ Telegram
+ Facebook?
+ Twitter?
+ Mastodon?
+ Nostr (preferred)


### Characteristics

Material cost at maximum of 100 euros


### Technical Part

Connections

+ LoRa + Arduino
+ Internet
+ Equipment

Repeater station



Equipment
=========


## Home box

These are the equivalent of an Alexa, except they are disconnected from Amazon servers and you know what is running inside.
The intention is to provide a larger box that stays in the living room connected to energy (USB or solar) and provides updates on the screen about what is happening on the region or across the news. Should also provide info about temperature and other metrics.

The preferred screen is ePaper to keep the information visible 24/7 without disturbing with light emission or using unnecessary energy. These home boxes are not intended to so actively used as for example the handheld, where you can even play games. The boxes are intended as home assistants. One possible expansion in the future is to accept voice commands customized by users. In ideal scenario this box replaces the local radion and Alexa assistants for everyday household talks while also giving information about what is happening around the house/region.

+ Touch screen
+ TFT display initially
  + E-ink preference
+ Wooden box
+ Rechargeable AA batteries (x4)
+ Network cable to connect antenna/power
  + when antennas are at long distance (e.g. rooftop)
+ Speaker
+ Microphone
+ Play radio, music
  + web radio
  + local music collection


## Solar gateway

These are the main antennas that connect different devices within a local area up to 8 kilometers of range.

Solar panels power the gateway with an included battery that permits to function up to three days without recharges.
The antennas are ceramic-based about the size of an arm (40 centimeters) to achieve longer distances.

Each gateway should be placed at a high position (e.g. top of a building, tree or tower) that is above the visibility line of other obstacles. Attention should be placed on the permission from other parties to install a gateway and to prevent theft of the gateway. When other gateways are at reach then it will act as a repeater to extend the range. The antenna reach is aggravated by climate conditions such as rain and fog. When connecting gateway repeaters, they should be placed at least one kilometer before the max reach of each other.

Pictures are taken by the gateway at 1 hour periodic intervals and made available for receivers. The image includes information such as local time, temperature, solar exposition and humidity values. This is useful for weather tracking/predicting purposes.

Given the antenna high-sensitivity and 24/7 operation then it might be possible to receive LoRa signals from satellites in orbit through https://github.com/G4lile0/tinyGS and this possibility will be investigated.


Features:

+ Long-range external antenna
+ Solar panel
+ GPS module
+ Measurement of temperature/humidity
+ MPTT with USB output
  + As this is expensive, a small circuit is more cost-effective
+ Camera to take local photos of nature/view
+ Battery for 3 days without sun
+ Measurement of temperature, humidity, solar exposure
+ Thunderstorm detection (optional)
+ Satellite receiver/relay


## Handheld

This device is carried by end-users. It is intended as a swiss-digital knife for the outdoors. On the first iteration it is not possible to make it as rugged and waterproof as preferred but shall nevertheless be packed with useful features for those who connect with autonomous networks on the outdoors. The device uses normal AAA batteries that can be replaced and recharged easily. Features a solar panel for recharging when there is no access to a power bank. In addition to hardware sensors with specific functionality, it permits to install apps, play games, send emails, read news and talk with other people across the world.

Characteristics:

+ Printed in wood+plastic combination
+ Transparent plastic to protect screen
+ push buttons also in wood
+ powered by two AA rechargeable batteries
  + possibly three AAA to provide 4.5 V
+ e-Ink display
  + with backlight
  + initially TFT (cheaper cost)
+ Solar panel
  + enough to charge the two batteries
  + protected by transparent plastic

### Front lights/sensors
+ flashlight (programable multi-color led)
+ uvc led (germ sterilization)
+ infrared receiver/emitter (for TV control)
+ led laser pointer
+ PIR Motion Sensor
+ night vision camera
  + price goes over 100 EUR budget
+ lightning detector?
  + price is around 25 EUR, users can choose

+ microphone
+ speaker with loud speaker mode
+ piezo buzzer
+ neodimium magnets (attach phone to surfaces)
+ NFC read/write
+ wifi / bluetooth
+ usb-c for charging
+ aim for visually impaired support
  + voice recognition and text to voice
+ vibration motor for notifications
+ vibration sensor
x super-capacitor as backup battery
+ temperature sensor

### Expansion ports
+ extension port available (molex with DAC)
+ external connection pins available
  + possibly reuse USB connector
  + or make available 3 pins (1 clock, 2 for voltage)
  + expand to other devices


### Outside handheld shell
+ 3d printed
+ outside faces made of wood/plastic
+ middle face with plastic that shines in dark
+ metal screws for opening and closening
+ transparent plastic for scratch protection
  + protect display, solar panel, lights
+ lid for water protection on usb charger

### Handheld Keyboard
+ direction keys
+ OK / back buttons
+ power on/off
+ gameboy style


# Apps (core)

### App: Launcher
+ GUI to launch apps
+ default app when starting
+ similar to Android devices
+ permit to choose background
+ permits customized themes/colors

### App: Installer
+ similar to apt-get and Android Play store
+ common text files and tutorials
  + available from the gateway
+ HTML-based documents
  + include text
  + include images/animations
+ choose regions/favorites
+ Install/update/remove apps
+ Can install from 3rd party
+ command line version available

### App: Settings
+ configure settings
+ choose language/region/time fuse
+ define privacy permissions
  + e.g. visible to others/contacts
+ define password
+ customize sounds/themes/actions
+ change power settings
  + e.g. disable Wifi/Bluetooth modules
+ option to act as gateway repeater
  + battery intensive option

### App: Files
+ can read/write text files
  + optionally simple excel/csv files
+ Play media files (images, music)
+ Share files with nearby contacts
+ Synchronize selected files/folders
  + with contacts

### App: Walkie-talkie
+ choose a contact
+ press the OK button to talk
+ records a voice message and sends

### App: Navigator
+ See people/devices nearby
  + lists distance to contacts nearby
+ Places nearby
  + uses curated list of places on region
+ show distance and orientation
  + initially not realtime

### App: Email
+ worldwide coverage
+ relayed by other gateways
+ hosted on device itself
+ limit to 20 MB
+ similar to winlink.org

### App: Chat
+ Chat with nearby/available users
  + group chats
  + notifications
+ communicate offline to other messengers at reach
  + without LoRaWan gateway when not available/desired
  + prefers direct link when contacts are at reach
+ send/share files/folders through chat

### App: Media player
+ play music from SD card (e.g. mp3)
+ see pictures, small videos

### App: NFC
+ NFC functionality
+ share cards with contacts
+ card feature (accept/deny access (to events, places)
+ add icons/description to cards
+ add time limit for shared cards
+ QR code reader/writer

### App: Backup
+ backup apps/docs/preferences to region server
+ data encrypted on server by user-defined password
+ periodic/scheduled
+ when moving to new device
+ synchronize preferences on multi-device

### App: Wifi
+ Hotspot
  + share files through wifi
  + web browser with region services
  + chat
  + news
+ use local wifi to reach gateway
  + useful when away from LoRa network
  + preference to LoRa when available
  + auto-connect to known wifis
  + global wifi login functionality

### App: Radio
+ listen to FM radio
  + automatically search and add list with RDS
+ listen to LoRa radio stations
  + fixed channel emission

### App: TV remote
+ create TV remotes
  + learn IR buttons
  + play IR buttons

### App: Automation
+ macro functions
  + press remote control button from TV
  + perform specific action
  + e.g. send message on specific chat
  + play a music playlist
  + turn off lights
+ shake phone
  + activate button or action
+ motion detection with IR receiver/sender
+ make device speak specific texts

### App: Console
+ run linux-like commands from CLI
+ launch CLI apps, see output
+ permit remote session (e.g. telenet)
+ text files with scripting language
+ use available sensors
  + either directly from pin output
  + or using alias for defined sensors


# Apps (goodies)

### App: Screenshot
+ take screenshots of screen
+ optionally make animated videos
+ hotkey to start/pause recording
+ can include pictures from camera

### App: Geocaching
+ submit geocaching places to discover
  + include description/difficulty
  + update status (active, inactive)
+ log discovery by user
+ give score
+ add comments

### App: News
+ see news from contacts and region
+ twitter-like announcements, comments and votes
+ submit events
  + set reminders (for day/hour)
  + rate event
  + permit recurring periodic events
  + add ratings/comments

### App: Podcast
+ hear podcasts
  + from contacts, topics, regions
+ editor for creating podcasts
  + can include start/ending sequence
  + include sound effects while recording
  + can include summary before intro sound
  + image cover for screenshot
+ Whisper on gateway-level
  + create subtitles/text version
  + create translations
+ include tags (region, date, topics, age level)
+ add feedback (likes, #plays, comments)
+ set time limits (e.g. 5 minutes)
  + visualize time progress


### App: Games
+ Snake
+ Bantumi
+ Chess (1v1 and alone)
+ Memory (Simon)
+ Slay
+ Gameboy emulator
+ Piano teacher/player
+ Cards (patience, blackjack)

### App: Wallet
+ Monero and Bitcoin wallet
+ Possibly other coins
+ synchronizes to region server
+ Receive payments
  + generate QR code on screen
  + connect through NFC
  + show equivalent in local fiat currency
+ Make payments
  + through NFC contact
  + through chat message

### App: Weather
+ temperature on nearby stations
+ weather prediction next days/hours
+ graphs of rain/temperature

### App: Timer
+ Time of the day
+ Countdown and stopwatch timers
+ Wake up Alarm
+ Synchronized timer
  + synchronize with selected contacts
  + joint warning/notifications

### App: Extras
+ Laser pointer
+ UVC germicide
+ Flashlight
+ Multicolor RGB/pattern
+ Dog whistle (using piezo buzzer)
+ Mosquito/Roedent repellent (using piezo buzzer)
+ Human approaching alarm

### App: Third-party hardware integration
+ Garmin
  + Send map location to Garmin
  + receive text notifications on Garmin

### App: Third-party software integration
+ Telegram (read/write messages)
+ IRC (read/write messages)
  + keep-alive, auto-register/login
+ email (read/write messages)
  + based on IMAP
+ nostr, twitter and mastodon instances
  + read/write/fav/retweet posts

### App: Chatbot
  + Connect to chatGPT
  + answer to voice questions from user
  + translate text
  + send reply as text message

### App: Wallpaper
+ show time, temperature average
+ when sun sets/raises
+ people nearby
+ notifications from news/chats/etc
+ configurable by user

### App: Birthdays
+ visualize contact birthdays
+ not including birth year
+ notify 3 days before
+ notify on same day
+ send greeting message/voice
+ view greetings from past years

### App: Marketplace
+ sell local products/services
+ connect farmers to buyers
+ remote payment with crypto currency

### App: Oscilloscope
+ use the expansion port
+ visualize the frequencies
+ detect type of component (diode, resistor, diode)
  + display value of diode, voltage received



# ESP32 software available today

## Network

### LoraWan standalone server
+ https://github.com/xoseperez/standalone-lorawan-gateway-balena
+ https://www.chirpstack.io/

### ESP32 as LoRaWan gateway
+ https://emanuelepagliari.it/2020/10/12/how-to-build-lorawan-gateway-heltec-esp32-lora/

### Sub-gHz antenna modulation
+ https://github.com/antirez/protoview

### ESP32 walkie-talkie with data
+ https://github.com/MordFIdel/SOCORAD32

### Sat transceiver
+ https://www.sparkfun.com/products/21287
+ https://swarm.space/product/swarm-asset-tracker/
+ https://othernet.is

### Autonomous network
+ https://unsigned.io/website/rnode/
+ https://reticulum.network/
+ https://github.com/markqvist/lxmf
+ https://github.com/markqvist/nomadnet
+ https://markqvist.github.io/Reticulum

### USB host
+ https://github.com/sdima1357/esp32_usb_soft_host

## Development

### Arduino simulator
+ https://wokwi.com/

### Updates OTA for ESP32
+ https://hackaday.com/2022/12/13/push-esp32-over-the-air-updates-from-github/

### Flash Arduino using Java
+ https://www.esp32.com/viewtopic.php?t=13853

### Running .NET on ESP32
+ https://sandervandevelde.wordpress.com/2022/12/15/fun-with-nanoframework-running-net-charp-on-esp32/


## Graphics

### Menu library for Arduino/RTos
+ https://lvgl.io/
+ https://github.com/davetcc/tcMenu
+ http://embeddedlightning.com/ugui/
+ https://github.com/ImpulseAdventure/GUIslice

### LVGL menus and operating system
+ wifi and status bar
  + https://www.youtube.com/watch?v=r62vfOhWXeo
  + https://github.com/0015/ThatProject/tree/master/ESP32_LVGL/LVGL8/3_BaseProject_Network_Selector
+ tutorial explaining LVGL menus and status bar
  + https://www.youtube.com/watch?v=CfsUQE495iA
+ excellent phone-like menu
  + https://www.youtube.com/watch?v=HOP7OMvAePs
  + https://github.com/fbiego/Lumia-ESP32


## Displays

### Creating VGA signal by cable
+ https://github.com/bitluni/ESP32VGA
+ https://github.com/marciot/ESP32CompositeColorVideo

### Control VGA/HDMI devices (power, brightness)
+ https://github.com/tttttx2/ddcvcp

### Creating TV signal by cable (good for games)
+ https://bitluni.net/esp32-composite-video

### More recent TV signal method:
+ https://github.com/aquaticus/esp32_composite_video_lib

### Broadcasting TV signal
+ https://github.com/cnlohr/channel3

### Teletext
+ https://github.com/peterkvt80/vbit2
+ https://github.com/xavery/ttxinfo
+ https://github.com/debackerl/telxcc

### HDMI adapter for ESP32
+ https://github.com/techtoys/HDMI-Shield/tree/master/Ra8876_Lite


## Radio

### AM radio transmitter (no extra hardware)
+ https://github.com/bitluni/ESP32AMRadioTransmitter
+ https://bitluni.net/am-radio-transmitter

### VHF/UHF transceiver
Costs ~100 EUR
+ https://www.kickstarter.com/projects/749835103/hamshield-for-arduino-vhf-uhf-transceiver
+ https://www.hobbypcb.com/products/uhf-vhf-radio/rs-uv3a


## Bluetooth
+ https://github.com/T-vK/ESP32-BLE-Keyboard (ESP32 as bluetooth keyboard)
+ https://github.com/T-vK/ESP32-BLE-Mouse (ESP32 as bluetooth mouse)


## Infrared
+ https://github.com/Arduino-IRremote/Arduino-IRremote
+ https://github.com/DjordjeMandic/Universal-IR-Blaster-TV-B-Gone


## Electronic tools

### Oscilloscope
+ https://github.com/botofancalin/M5Stack-ESP32-Oscilloscope

### Multimeter
+ https://github.com/har-in-air/ESP32_MULTI_METER
+ https://github.com/gavinlyonsrepo/LCR_meter
+ https://github.com/YordanYanakiev/LC-Fr-Meter-for-ESP32

### OBD2 car diagnostics
+ https://github.com/meatpiHQ/wican-fw


## Emulators

### Emulate DOS/FreeDOS on ESP32
+ http://www.fabglib.org/index.html
+ https://www.youtube.com/watch?v=P_kpwbIkFjo

### ESP32 8-bit game arcade
+ https://www.youtube.com/watch?v=Ra-IzbRg0bM
+ https://www.crowdsupply.com/byte-mix-lab/microbyte
+ https://github.com/jfm92/microByte

### ESP32 play Doom
+ https://www.youtube.com/watch?v=y6PP_IBbOTY
+ https://github.com/jkirsons/doom-espidf


## Internal compilers and scripts

### Compile/script C code to run on ESP32
+ https://www.codeproject.com/Articles/5061494/Run-a-C-Language-Interpreter-on-Your-ESP32
+ https://github.com/sellicott/tcc-riscv32

### Compile Java code to run on arduino
+ https://developer.microej.com/microej-sdk-software-development-kit/


## Boot and binary loaders
+ https://github.com/sookmook/OTA_basic
+ https://baldwisdom.com/bootdrive/
+ https://arduino.stackexchange.com/questions/19489/load-arduino-flash-code-from-sd-card
+ https://stackoverflow.com/questions/36100030/run-arduino-sketch-from-an-sd-card


## Virtualization

### Virtual Machines for ESP32
+ https://github.com/toitlang/jaguar
+ https://github.com/juiceRv/JuiceVm
+ https://haiku-vm.sourceforge.net/
+ https://github.com/TOPLLab/WARDuino
+ https://dmitry.gr/?r=05.Projects&proj=12.%20uJ%20-%20a%20micro%20JVM
+ https://blog.toit.io/why-doesnt-v8-fit-on-my-microcontroller-71dc6e2d8f5c
+ https://github.com/atomvm/AtomVM
+ https://github.com/Moddable-OpenSource/moddable

### Generic virtual machines emulators
+ https://github.com/drorgl/esp32-tinyemu (runs linux)
+ https://github.com/LekKit/RVVM

### Scripting languages
+ https://github.com/berry-lang/berry (C/Java alike)
+ https://github.com/micropython/micropython
+ https://www.espruino.com/ (javascript)
+ https://github.com/edmundmk/kenaf (LUA alike)
+ https://eluaproject.net/ (LUA scripting language)
+ https://www.embedvm.com/ (C alike)
+ https://github.com/cesanta/mjs
+ https://github.com/robinhedwards/ArduinoBASIC (Basic)

### Operating system for ESP32
+ https://nuttx.apache.org/
+ https://github.com/AlixANNERAUD/Xila
+ https://github.com/renamedquery/esp32-pc
+ https://github.com/PQCraft/EZBCOS
+ https://github.com/botofancalin/M5Stack-MultiApp-Advanced
+ https://github.com/sukesh-ak/ESP32-TUX/
+ https://github.com/embox/embox (not yet supported officialy)
+ https://mongoose-os.com/
+ https://github.com/jcmvbkbc?tab=repositories (native Linux port)
+ https://www.riot-os.org/

### Bash environment on ESP
+ https://github.com/dani007200964/Shellminator
+ http://sebastian-duell.de/en/microbox/usage.html


## Kernel features

### ExFat support on ESP32
+ http://elm-chan.org/fsw/ff/00index_e.html

### SSH server/client in ESP32
+ https://registry.platformio.org/libraries/ewpa/LibSSH-ESP32


## Cybersec

### ESP32 deauther
+ https://github.com/GANESH-ICMC/esp32-deauther

### ESP32 create spam wireless lans (and send random wifi packets)
+ https://github.com/Jeija/esp32-80211-tx

### VNC and multi-environment
+ https://github.com/0015/ESP32Berry

### Wireguard
+ https://github.com/ciniml/WireGuard-ESP32-Arduino

### Multiple offensive tools
+ https://github.com/justcallmekoko/ESP32Marauder/
+ https://pwnagotchi.ai/


# Other links

## Cryptocurrencies
+ https://github.com/revoxhere/duino-coin
+ https://github.com/Eroic/ESP32_Bitcoin

## Voice

### Voice recording/playback
+ https://en.wikipedia.org/wiki/Opus_(audio_format)
+ https://github.com/mkopa/opus-codec-arduino
+ https://github.com/atomic14/diy-alexa
+ https://github.com/earlephilhower/ESP8266SAM
+ https://github.com/earlephilhower/ESP8266Audio
+ https://github.com/ArminJo/Talkie

### Voice recognition/assistant
+ https://github.com/espressif/esp-skainet
+ https://github.com/ggerganov/whisper.cpp

### Home automation
+ https://esphome.io/
+ https://esphome.github.io/bluetooth-proxies/

### Energy harvest (battery free)
+ https://www.freethegameboy.info/
+ https://www.hackster.io/news/andreas-eriksen-s-potatop-is-a-lisp-powered-laptop-with-a-battery-life-measured-in-years-2f5d79653f24


## Games

### Donkey kong, Pac-man, Galapa
+ https://github.com/harbaum/galagino
+ https://github.com/VolosR/M5SpaceWars
+ https://github.com/VolosR/M5StickCAlienAttack
+ https://github.com/VolosR/M5StickCPlusBrakeout
+ https://howtomechatronics.com/projects/arduino-game-project-replica-of-flappy-bird-for-arduino-on-a-tft-touch-screen/
+ https://www.instructables.com/Text-Based-Multi-Choice-Adventure-Game/


## Misc

### SD reader with ESP32 glueds
+ https://github.com/Neutrino-1/Wireless_SD

### Anti-teenager sound (entertainment)
+ https://www.youtube.com/watch?v=MbYKhEtCRIs

### Morse code learning
+ https://github.com/scottlbaker/morseKeyers

### Web browsing examples
+ https://github.com/rebane2001/chanduino
+ https://libwebsockets.org/git/libwebsockets/tree/READMEs/README.html-parser.md


# Partners

+ https://frn.dc4fs.de/
+ https://github.com/jfm92/microByte
+ https://en.wikipedia.org/wiki/Cybiko
+ https://www.patrick-breyer.de/en/posts/chat-control/


# Device designation

+ each device model starts with one specific letter
+ defines CPU architecture
+ OS uses X.Y numbering
+ libraries/apps use semver
+ device codename is separated from software



### Types of device models
+ M = mobile handheld
  + MM = mobile minimal
  + ME = mobile e-paper
  + MW = mobile wrist
+ H = home/house
+ A = Auto/wheels
  + AUTO = cars
  + AM = motorbikes
  + AB = bikes
+ A = airplane/flying
  + AIR = airplane
  + AD = drone
+ N = nautic
  + NV = vessel
  + NS = submarine
+ G = gateway/repeater
+ S = server/bridge
+ B = beacon
+ S = space-related
+ SGS = ground station
+ SAT = satellite


### Examples
+ Radio3 MM-1.0
+ Radio3 ME-1.0



# Feedback

Feedback collected from people around the internet about this kind of device.

> "The glaring problem, sadly, is that there's nothing you can actually _do_ with it. There were no games of any quality, and the mesh networking would only work over a short range and if somebody else had one, which meant that feature was useless in the suburbs."

> "This was my first big purchase in life, when I was 12. When i brought it to school, I would discover the 2 other students who also had a cybiko through its wireless network, and chat and play games with them. It was really cool and a special club to be in."

> "That was something I was hoping we will get on Apple Watch walkie-talkie feature. Unfortunately the features depends on having a stable internet connection and never worked for me reliably. The world needs more P2P."

> "It's amazing how P2P basically doesn't exist anywhere. Open source got taken over completely by federated/self hosted, or Blockchain. We have really good long range Bluetooth and LoRa and yet there is not one decent affordable alternative to decades old analog FRS after all this time."

> "It is like a crime against all of technology that there is no equivalent of this today.
We have smartphones, but battery life sucks and they have no real local mesh support, and no expansion port. We have lots of dev boards, but no real finished products without exposed PCBs, and with a proper app-capable OS. And the ones that are reasonably polished are far too expensive for a semi-novelty. The closest is maybe... pwnagotchi? A graphing calc?

> "I just want like, a little ESP32 handheld, with an m.2 slot or something in the traditional place for cartridges, and the ability to run apps from files on SD cards(Even if they're just MicroPythons). But somehow all the "Hacker's handhelds" and the like seem to go nowhere, and are basically just an Arduino with a screen, meanwhile phones never get the expansion pack and local mesh capabilities the cybiko had. Cybiko was a lot of fun. It would have been better with some AAA games, but it was still awesome."



### Links to feedback
+ https://www.youtube.com/watch?v=ojatBoMZubk
+ https://news.ycombinator.com/item?id=30485353




# Hardware research


## Feedback

+ 2023-02-24: TFT kit arrived and worked as expected. The kit model is ESP32-2432S028R from https://www.aliexpress.com/item/1005004913471113.html for 15,29€ that includes shipping. Software is difficult to obtain and poorly documented but was collected on the radio3 repositories.

+ 2023-01-27: ePaper kit was experimented, but the screen refresh rate was not satisfactory for usage with LVGL. Alternative is using a TFT based screen which is cheaper (~15 euros) and comes with an LVGL demo by default (fit for purpose)



## Combo kits

These are sets that already contain ESP32 + Screen + Touchscreen. On these cases it is only necessary to add the LoRa module to have a working handheld.
Reduces complexity, size and costs when compared to buy them separately. At a later point might be possible to order kits with the LoRa and GPS modules built inside.


### Candidates

+ 46.41€ (37,15 + 9,26) LILYGO T5 4.7 inch E-Paper ESP32 Development Board Ink Screen Display Module ESP32-WROVER-E 16MB FLASH 8MB PSRAM WIFI Bluetooth
https://www.aliexpress.com/item/1005002116919184.html?aem_p4p_detail=20230106074942598179120840000004300778&algo_exp_id=2dcc9fdd-e98b-4153-ab87-314fd235dd27-2&pdp_ext_f=%7B%22sku_id%22%3A%2212000018795984638%22%7D&ad_pvid=20230106074942598179120840000004300778_3&ad_pvid=20230106074942598179120840000004300778_3
2023-01-09: updated price to 34.39€

+ 18.59€ (11,03 + 7,56) LILYGO T5-4.7 inch E-paper ESP32 V3 Version Capacitive Touch Cover 16MB FLASH 8MB PSRAM WIFI/Bluetooth for Arduino
https://www.aliexpress.com/item/1005002272555887.html?gps-id=pcDetailBottomMoreThisSeller&_t=gps-id:pcDetailBottomMoreThisSeller,scm-url:1007.13339.291025.0,pvid:86f98735-24a6-4613-aadc-65430534ea6d,tpp_buckets:668%232846%238113%231998&pdp_ext_f=%7B%22sku_id%22%3A%2212000022167838227%22%2C%22sceneId%22%3A%223339%22%7D

+ 6.34€ LoRa 868MHz 915MHz LLCC68 Wireless Module 22dBm Long Range 5km CDEBYTE E220-900T22D SMA-K UART RSSI Transmitter Receiver DIP
https://www.aliexpress.com/item/1005002116919184.html?aem_p4p_detail=20230106074942598179120840000004300778&algo_exp_id=2dcc9fdd-e98b-4153-ab87-314fd235dd27-2&pdp_ext_f=%7B%22sku_id%22%3A%2212000018795984638%22%7D&ad_pvid=20230106074942598179120840000004300778_3&ad_pvid=20230106074942598179120840000004300778_3


71.34€ for the three basic modules


## Screens

Possible screens to adopt from en ePaper perspective.
Unfortunately they have slow update rate, which makes them poorly responsive to GUI applications.
They are nevertheless good base stations in the living room to show data 24/7.


### Candidates

+ 19,97€ 1.54 Inch 4 Grayscale E-Paper Display With Frontlight Eink Screen, GDEW0154T8-FL
https://www.aliexpress.com/item/4000202574621.html

+ 13,80€ 1.54'' Epaper 200x200 SPI Cheap E-ink Display, GDEW0154T11 (200x200)
https://www.aliexpress.com/item/1005003790815924.html

+ 28,37€ 4.2 Inch E-Ink Panel SPI Interface Buy 4 Grayscale Epaper Display, GDEW042T2
https://www.aliexpress.com/item/32812327103.html?algo_exp_id=1c951103-3ed8-4f1c-9430-5086965c10e3-6&pdp_ext_f=%7B%22sku_id%22%3A%2212000020930355822%22%7D

+ 19,72€ 2.66inch SPI 3-Color E Paper Epaper Eink E-ink E-Paper Screen Display Module for Arduino Raspberry Pi Zero 2 W WH 3A 3B Plus 3 4
https://www.aliexpress.com/item/1005001852222187.html?gps-id=pcDetailBottomMoreThisSeller&_t=gps-id:pcDetailBottomMoreThisSeller,scm-url:1007.13339.291025.0,pvid:c80c0634-4273-424a-b275-4c979df11bde,tpp_buckets:668%232846%238110%231995&pdp_ext_f=%7B%22sku_id%22%3A%2212000017858875016%22%2C%22sceneId%22%3A%223339%22%7D



## Solar panels

Each handheld should be equipped with a solar panel large enough to provide a realistic power charge.
Not all countries enjoy multiple hours of sunlight across the year, nevertheless we make this option available as secondary charger method when a stable power source is not available. The current configuration is based between two or three AA/AAA batteries to provide around 3 to 4.5 volts of power. These solar panels are placed on the back side of the handheld device.

Using a "joule thief" circuit and solar battery chargers is possible to deeply extract the energy inside these batteries. The solar charger is maximized in terms of usability. A 60 minutes charge in the sun should provide, at minimum, 20 minutes of non-intensive usage (e.g. exchange LoRa messages or GPS position). The handheld needs to support the scenario of staying several hours exposed to the sun.


### Candidates

+ 1.55€ 98x63 mm solar panel
https://www.aliexpress.com/item/1005002777632698.html?algo_exp_id=4590d8dc-6c4d-42a2-ab15-36c787febf7f-16&pdp_ext_f=%7B%22sku_id%22%3A%2212000022139931386%22%7D

+ 16.00 € 1W 6V Flexible Solar Panel Small Thin Amorphous Silicon Solar Cell Waterproof Camping Portable Power Solar Panel for Light Phone
https://www.aliexpress.com/item/1005002808274737.html?gps-id=pcDetailBottomMoreOtherSeller&_t=gps-id:pcDetailBottomMoreOtherSeller,scm-url:1007.40000.320561.0,pvid:5cf26341-d0cd-4cc5-9edf-395cf2a443cd,tpp_buckets:668%232846%238110%23373&pdp_ext_f=%7B%22sku_id%22%3A%2212000022282791254%22%2C%22sceneId%22%3A%2230050%22%7D

+ 1.27€ AAA Battery Step Up to 5V Power Converter Module for Arduino
https://www.aliexpress.com/item/32840471284.html?algo_exp_id=0d318cbc-06ac-4ffc-b05c-eed0f292ab32-34&pdp_ext_f=%7B%22sku_id%22%3A%2265098526413%22%7D

+ 5V DC DC Converter Step Up Power Supply DC-DC Booster Boost Buck Converter Board Step-Up 500MA Voltage Regulator 1V-5V to 5V
2.25€ https://www.aliexpress.com/item/32813355879.html?aem_p4p_detail=202301030140566407151039941540000262270&algo_exp_id=e7fb92a6-d931-4899-a1af-e2b800723c21-1&pdp_ext_f=%7B%22sku_id%22%3A%2264552758650%22%7D&ad_pvid=202301030140566407151039941540000262270_2&ad_pvid=202301030140566407151039941540000262270_2



## Sensors / peripherics

The handheld device goes beyond the normal functionality expected by a communication device. It should be the electronic equivalent of a swiss-knife in your pocket and contain as much hardware functions as we are able to include within the available budget of 100 euros.

For this reason are investigated the usage of PIR leds, NFC, laser beams and other related hardware. It is likely that not all of these circuits find their way to the handheld due to size and pin limitations.


### Candidates


+ 2.50 € PIR led 1pcs HC-SR505 Mini Infrared PIR Motion Sensor Precise Infrared Detector Module For Arduino Body Sensor Switch Module Sensing:
https://www.aliexpress.com/item/1005002969815153.html?aem_p4p_detail=202212301514284970052950069430014760355&algo_exp_id=5c282359-db7c-439f-ab15-41e517d82f5a-1&pdp_ext_f=%7B%22sku_id%22%3A%2212000023030130119%22%7D&ad_pvid=202212301514284970052950069430014760355_2&ad_pvid=202212301514284970052950069430014760355_2

+ 25,10 € Sensor for sky lightnings (AS3935) compatible with Arduino - DFRobot SEN0290
https://mauser.pt/catalog/product_info.php?cPath=1667_2669_2671&products_id=095-0749

+ 17.42€ Heltec Lora Node ASR650x CubeCell Module/Development board 433MHZ/868-915MHZ for arduino/Lora sensors waterproof IP67

+ 32.17€ 2 pieces CubeCell Lora Node ASR6502 LoRa with 1 / 2AA battery case LoRaWAN node apps for arduino with antenna and connector
https://www.aliexpress.com/item/4001219888480.html?algo_exp_id=679a31b1-6ee9-4c20-bbd6-1e5eb331ee65-31&pdp_ext_f=%7B%22sku_id%22%3A%2210000015341499508%22%7D

+ 55.54€ // LILYGO® T-Echo NRF52840 SX1262 433 / 868 / 915MHz Module LORA GPS 1.54 E-paper BLE NFC for Arduino
https://www.aliexpress.com/item/1005002870936996.html?gps-id=pcDetailBottomMoreOtherSeller&_t=gps-id:pcDetailBottomMoreOtherSeller,scm-url:1007.40000.320561.0,pvid:eb752a30-4a93-43ee-9c9b-cd9d8c9db858,tpp_buckets:668%232846%238110%23373&pdp_ext_f=%7B%22sku_id%22%3A%2212000022561082653%22%2C%22sceneId%22%3A%2230050%22%7D

+ 31.99€ DollaTek LoRa32 V2.1 868MHz ESP32 LoRa SD Card WiFi Wireless Module with SMA IP5306 0.96 Inch OLED
https://www.amazon.de/-/en/gp/product/B07RWYJQPT/ref=ox_sc_act_title_2?psc=1

+ 6.70€ 5PCS Deep LED Diode UVC SMD LED 3535 UVC 270nm 280nm 3~6mW Chip Ultraviolet Light Beads
https://www.aliexpress.com/item/1005004897087950.html?aem_p4p_detail=202212301155178757628550149710011152371&algo_exp_id=349b8ac0-e04c-4adb-b6b3-1738649bb081-2&pdp_ext_f=%7B%22sku_id%22%3A%2212000030936857181%22%7D&ad_pvid=202212301155178757628550149710011152371_3&ad_pvid=202212301155178757628550149710011152371_3

+ 2.60€ 2pcs 650nm 5mw Laser Diode Module Red Color TO-18 DIY Laser Sensor Diode 2.2-2.4V LED Electronics Design
https://www.aliexpress.com/item/1005001714710739.html?algo_exp_id=6447d058-69be-45bd-9929-d4fbb5afd8f8-13&pdp_ext_f=%7B%22sku_id%22%3A%2212000017266545749%22%7D

