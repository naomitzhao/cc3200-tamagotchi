# CC3200 Tamagotchi

Sandeep Reehal and Naomi Zhao

## Project Description

Our project is the CC3200 Tamagotchi, a spin-off of the classic hand-held "Tamagotchi" game, in which a user raises and plays minigames with a virtual pet. Using a TI CC3200 board connected to various inputs and outputs, we created a device that displays the game state and visuals on an Adafruit OLED and shows warning signals on an external LED. The game is controlled primarily by an IR TV remote and the on-board accelerometer. TV signals are used as inputs in game navigation and minigames, and the accelerometer is used in minigames.

### Main Screen

Gameplay is centered around a main screen that shows the virtual pet using an animated, stylized graphic of a cat sitting in a box. Status bars are shown at the bottom, with blue corresponding to experience (XP), yellow corresponding to hunger, and red corresponding to happiness. Hunger and happiness decrease over time, and must be increased via the feeding or playing minigames to keep the pet from running away, as shown in Figures 2 and 3. XP can be increased by the training minigame, and at certain experience thresholds, the pet levels up. The current level and XP are displayed on the game main screen above the status bars. At a certain level threshold, which we set to level 4, the size of the pet increases, or scales up, showing growth of the pet. 

<img src=https://github.com/user-attachments/assets/7c694b29-2434-44a5-8126-311c06ed911c width="300" height="200"/>
<img src=https://github.com/user-attachments/assets/e9665ec6-e7db-45aa-94c1-18a40f1e6bea width="300" height="200"/>
<br/>
<img src=https://github.com/user-attachments/assets/8f825190-8832-4daf-89a0-cd70d0b6ea65 width="300" height="200"/>
<img src=https://github.com/user-attachments/assets/1eb5f468-1119-4e99-ae2b-14c94abd846c width="300" height="200"/>
<br/>

### AWS Connection

The CC3200 also connects to an AWS server via a SimpleLink WiFi connection. It modifies an AWS device shadow thing that represents the current state of the pet. This AWS device shadow is used for saving the game and loading existing saves on the CC3200. The information on the device shadow can also be accessed from a web interface that displays the pet GIF, level, experience, and status bars, similarly to the OLED interface. The web interface also features options to feed and play with the pet.

<img src=https://github.com/user-attachments/assets/47ad1c3b-cc0a-4904-9054-773843b47497 width="300" height="200"/>

### Game Over and Warnings

When hunger or happiness reaches 0, the pet will "run away", erasing its save data and showing a special graphic on the screen. Before, then when hunger or happiness reaches 5 or lower, an attached LED will flash periodically to remind the player to feed or play with the pet.

<img src=https://github.com/user-attachments/assets/45cc1a5f-71d4-45da-9419-fe55d496e18f width="300" height="200"/>
<img src=https://github.com/user-attachments/assets/bbf8f09c-9bc5-4db8-b14c-0aba85625599 width="300" height="200"/>

### Unique Features

Although our project is based on the classic Tamagotchi handheld device, our rendition has some key differences that makes it stand out. For one, our virtual pet game allows the user to have multiple pets at once, unlike the original Tamagotchi, which only allows one. We implemented save and load mechanics via AWS, and added the ability to have two saves at once. When the device starts, the user is prompted to create a new save or load a save from either LOAD 1 or LOAD 2. Additionally, our virtual pet game uses cloud sync and has a web dashboard thanks to the on-board WiFi connection and our AWS server. This allows the user to view and take care of their pet even when the device is turned off. Finally, our implementation also uses AWS SNS to send email notifications when of the pets' hunger or happiness reaches 5.

<img src=https://github.com/user-attachments/assets/cfd0f861-02c3-4706-8ef6-e188d201d79e width="300" height="200"/>
<img src=https://github.com/user-attachments/assets/bc752b37-ebb0-474e-a980-d99386e407db width="300" height="200"/>
<img src=https://github.com/user-attachments/assets/cae0d454-8c9c-4659-ba9f-1221506cc45b width="300" height="200"/>

