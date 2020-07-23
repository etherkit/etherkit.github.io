---
title: Setting up the Arduino IDE for the Empyrean
keywords: empyrean, arduino, ide
summary: "How to install the Empyrean board support package for Arduino."
sidebar: empyrean_sidebar
permalink: empyrean_ide_setup
folder: empyrean
---

## Installing Empyrean Support in Arduino IDE
If you do not already have the Arduino IDE installed on your PC, please visit [https://arduino.cc](https://arduino.cc) to download the proper installer for your operating system. Install the program according to the provided instructions, and the proceed with the below instructions:

1. Open the Arduino IDE and then navigate to the Preferences screen by selecting the ```File``` menu, and then ```Preferences```. Click the small button to the right of the text box labeled ```Additional Boards Manager URLs```, and then paste the following URL into the windows which pops up:
[https://github.com/etherkit/ArduinoBoards/raw/master/package_etherkit_index.json](https://github.com/etherkit/ArduinoBoards/raw/master/package_etherkit_index.json)
<br>Click OK to close this window, and then OK to close the Preferences.
2. Navigate to the Arduino Boards Manager in the IDE by selecting the ```Tools``` menu, then ```Board```, and then ```Boards Manager...```. In the search box in the upper right of the Boards Manager windows, type ```SAMD```.
3. In the search results list below, find the entry for ```Arduino SAMD Boards```, select it with your mouse, and then click the install button.
4. Next, find the entry for ```Etherkit SAMD Boards```, select it, and click the install button. Close the Boards Manager window when this is complete.
5. In the ```Tools > Boards``` menu, you should now see Empyrean Alpha and Empyrean Beta listed as board options. Select the appropriate board in order to start uploading sketches to your Empyrean.

{% include links.html %}
