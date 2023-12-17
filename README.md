# vtr200b 
Simple control of Systemair vtr200b via modbus TCP (Wifi) directly to HA.

This particular project is for Systemair units with old displays featuring a wheel, as shown in this photo:

![img](https://i.imgur.com/BJba6Vp.png)

Credits to Ztaeyn I used his project as a template for this one, even for this README, lol.
* https://github.com/Ztaeyn/HomeAssistant-VTR-Modbus

With this, you can currently:
- Change operation mode (Low speed, Normal speed, High speed)
- Set the desired temperature on the VTR thermostat.
- View alarm status and filter replacement countdown.

Sources:
* Modbus codes: https://shop.systemair.com/upload/assets/MODBUS_FOR_RESIDENTIAL_D24810_USER_MANUAL_EN__A007_.PDF?91306fe4

NOTE: The addresses have an offset of -1 compared to the VTR user manual above.

My Control Panel is very simple, and the code is in this repository under the `user_interface` folder.

![img](https://i.imgur.com/32qOCJ4.png)

Hardware required (for my setup):
A Modbus TCP converter. I use the Waveshare RS485 PoE.
https://www.waveshare.com/wiki/RS485_TO_ETH_(B)

How to install this:
- Copy the packages folder to your HA installation folder and modify `configuration.yaml` to include this part:
```
homeassistant:
  packages: !include_dir_named packages
```
- Modify vtr200b.yaml with your working Modbus settings.
- Verify that HA configuration is OK and reboot.
- Copy my HA UI card layouts if you'd like.

How to configure RS485 PoE:

I found this video very useful for configuring RS485 PoE; it was not so straightforward, at least for me:

* https://www.youtube.com/watch?v=wEasws0fIVg&t=420s

Wiring:

![img](https://i.imgur.com/znc8YoE4.png)

My settings that work for my vtr200b:

![img](https://i.imgur.com/BJba6Vp.png)

![img](https://i.imgur.com/b6riAiK.png)

![img](https://i.imgur.com/LaLzI0J.png)
