# HA_Dishwasher_Status
Parts used:<br>
&ensp;•	Energy monitor<br>
&emsp;•	Shelly PM Plus (UL) for hardwired Dishwasher<br>
&emsp;•	Smart plug with energy meter for plugin dishwashers<br>
&ensp;•	Aqara Zigbee door sensor<br>
&ensp;•	OpenEPaperLink AP<br>
&emsp;•	https://www.tindie.com/products/electronics-by-nic/openepaperlink-mini-ap-v3-zigbee-wifi-gateway/<br>
&ensp;•	OpenEPaperLink Display (2.9”)<br>

Hardware Installs:<br>
&ensp;•	Shelly PM Plus (UL) (hardwired)<br>
&emsp;•	Install the relay according to the supplied directions intercepting the power to the dishwasher, can be installed in a electrical box behind the dishwasher, or the builtin electrical box on the dishwasher (if there is enough space)<br>
&ensp;•	Smart plug (plugin dishwasher)<br>
&emsp;•	unplug dishwasher and plug dishwasher into smart plug<br>
&ensp;•	Door sensor<br>
&emsp;•	Install door sensor on the dishwasher door<br>
&ensp;•	OpenEPaperLink<br>
&emsp;•	Plug in OpenEPaperLink AP and join to WiFi Network<br>
&emsp;•	Connect batteries to Display<br>

Integration:
  1.	Download OpenEPaperLink Integration from HACS
  2.	Under inegrations add OpenEPaperLink integration
  3.	When asked for IP Address you will find this on the display of the OpenEPaperLink AP display
  4.	AP and Displays should add to HA

Helpers<br>
&ensp;•	Add Threshold Sensor Helper (Dishwasher Running Status)<br>
&emsp;•	Name: Appliance State: Dishwasher<br>
&emsp;•	Entity: Shelly PM Plus (UL) Power (W)<br>
&emsp;•	Hysteresis: 0<br>
&emsp;•	Lower Limit: {blank}<br>
&emsp;•	Upper Limit: 1 (might have to set higher if yours idles higher then 1W)<br>
&emsp;•	Entity ID: binary_sensor. appliance_state_dishwasher<br>
&ensp;•	Add Dropdown Helper (Dishwasher Clean State, Optional if you want it on a dashboard)<br>
&emsp;•	Name: Appliance State: Dishwasher Clean Status<br>
&emsp;•	Options:<br>
&emsp;&ensp;*	Dirty<br>
&emsp;&ensp;*	Washing<br>
&emsp;&ensp;*	Clean<br>
&emsp;•	Entity ID: input_select. appliance_state_dishwasher_clean_status<br>

Automation:<br>

Create automation using the code at this link:<br>
https://gist.github.com/rustyk123/2b436d4a4254d5b6fab68f04a70c053a#file-gistfile1-txt<br>

update the entities to match your entities.<br>
