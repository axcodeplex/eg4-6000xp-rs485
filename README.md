# EG4 6000XP - SolarAssistant.io RS485 Direct Connection
Documentation of configuring and connecting the 6000XP directly to SolarAssistant via RS485

There seem to be a few paths here;
* Using a RS485/USB/RJ45 straight from the RPI/SA to the CT1 port on the inverter
  * Great summary thread on the subject in general; https://diysolarforum.com/threads/how-to-eg4-6000xp-and-sa-via-rs485.107604/
* Using the hard-wire posts in the bottom left of the control panel in the inverter
* Snagging the RS485 A/B connection from an HDMI breakout connector
* Snagging the RS485 A/B connections from the board directly where the HDMI plug board hooks to the inverters main board
   * These posts seems to give the pinout of the 4 pin going to the HDMI:
     * https://diysolarforum.com/threads/eg4-6000xp-18kpv-custom-rs485-dongle-connector.82011/page-6
     * and
     * https://diysolarforum.com/threads/eg4-6000xp-18kpv-custom-rs485-dongle-connector.82011/post-1378301
   * This post has a photo of the exact pins needed on the board:
     * https://diysolarforum.com/threads/eg4-6000xp-esphome.91662/post-1240909
* Suggested RS485/USB Adapter for non-CT1 connection: https://www.amazon.com/gp/product/B081MB6PN2
* Full on bananas custom flash of "ESP Home" (?) for the PIC in the HDMI Dongle:
   * https://github.com/dresslerc/eg4-6000xp-esphome/tree/main?tab=readme-ov-file


It seems the general consensus that the HDMI/Wifi Dongle **can not** be used at the same time as a direct RS485 connection (likely because they share the same physical connections back to the Inverters internal cpu)

Solar assistant's page on the matter: https://solar-assistant.io/help/inverters/eg4/IV-6000-XP-IN/rs485

**Big gap:** 
* Without EG4's tool, using "quick charge", or forced on-demand battery charging, is not easily possible **
* Per [This thread](https://diysolarforum.com/threads/eg4-6000xp-solar-assistant-home-assistant-quick-charge.88617/post-1171344) you can:
  * "toggle Byte0bit4 and/or Byte0Bit5 to 1 for CAN ID 0x35C. This will basically force charge the battery (even from AC) as long as the bit stays on."
