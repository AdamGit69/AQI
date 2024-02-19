# Air Quality Index Card For Home Assistant - Under Construction!

To use this card you will need AirVisual Cloud integration setup and you will need to sign up for a key.

To install AirVisual follow these steps:

  Go to Settings > Devices & Services.
  In the bottom right corner, select the  Add Integration button.
  From the list, select AirVisual Cloud.
  Follow the instructions on screen to complete the setup.

More info on the AirVisual integration can be found here: https://www.home-assistant.io/integrations/airvisual/

Once installed the integration will create enities called:
  sensor.chinese_air_pollution_level
  sensor.chinese_main_pollutant
  sensor.u_s_air_pollution_level
  sensor.u_s_main_pollutant

I use the US air pollution levels in this card. Anyway, once AirVisual is setup, save the images from this Github in your HA instance's WWW directory.
You need the following images saved:

  healthy-icon.svg

  moderate-icon.svg
  
  unhealthy-icon.svg
  
  hazardous-icon.svg

Then you need to copy and paste the code from the YAML file into a new "manual card" (add new card/right down the bottom)

And that's it. :)

![screenshot2](https://github.com/AdamGit69/AQI/assets/103038993/e08d3067-52b3-4b00-a68a-b22d30d9668e) <BR>
![screenshot1](https://github.com/AdamGit69/AQI/assets/103038993/aa299003-d028-416d-9a30-8e6c156da637) 
