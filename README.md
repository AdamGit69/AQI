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

I use the US air pollution levels in this card. Anyway, once AirVisual is setup, save the images from this Github in you HA instance's WWW directory.
You need the following images saved:

  unhealthy-icon.svg

  moderate-icon.svg
  
  unhealthy-icon.svg
  
  hazardous-icon.svg

Then you need to copy and paste the code from the YAML file (or below) into a new "manual card" (add new card/right down the bottom)

And that's it. :)


## CODE START


type: horizontal-stack
cards:
  - type: conditional
    conditions:
      - entity: sensor.u_s_air_pollution_level
        state: good
    card:
      type: markdown
      content: >-
        <center><img src='/local/healthy-icon.svg' width='50%'><BR>


        <font size = 4px> The Air Quality Today Is  <font color = reen> Good
        </font></font>


        The AQI is: <font size = 4px color = reen> {{
        states('sensor.u_s_air_quality_index') }} </font></center>
  - type: conditional
    conditions:
      - entity: sensor.u_s_air_pollution_level
        state: moderate
    card:
      type: markdown
      content: >-
        <center><img src='/local/moderate-icon.svg' width='50%'><BR>

        <font size = 4px> The Air Quality Today Is  <font color = yellow>
        Moderate </font></font>


        The AQI is: <font size = 4px color = reen> {{
        states('sensor.u_s_air_quality_index') }} </font></center>
  - type: conditional
    conditions:
      - entity: sensor.u_s_air_pollution_level
        state: unhealthy
    card:
      type: markdown
      content: >-
        <center><img src='/local/unhealthy-icon.svg' width='50%'><BR>

        <font size = 4px> The Air Quality Today Is  <font color = red> Moderate
        </font></font>


        The AQI is: <font size = 4px color = reen> {{
        states('sensor.u_s_air_quality_index') }} </font></center>
  - type: conditional
    conditions:
      - entity: sensor.u_s_air_pollution_level
        state: hazardous
    card:
      type: markdown
      content: >-
        <center><img src='/local/hazardous-icon.svg' width='50%'><BR>

        <font size = 4px> The Air Quality Today Is  <font color = red> HAZARDOUS
        </font></font>


        The AQI is: <font size = 4px color = reen> {{
        states('sensor.u_s_air_quality_index') }} </font></center>



