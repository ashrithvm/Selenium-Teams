# MS-Teams Meeting Joiner
  1. Selenium script to automatically join Microsoft Teams meetings.<br>
  2. Automatically turns off your microphone and camera before joining.<br>
  3. Automatic login and blacklist can be set in the config file.  
  4. Leaves either after a specified time, if you are the last person in the meeting or only if a new one is available<br>

## Configuration options  
  
- **email/password:**  
The email/password of your Microsoft account (can be left empty if you don't want to automatically login)  

- **run_at_time:**  
Time to start the script at. Input is a string of the hour and minute in 24h format, if you want it to start immediately leave this empty. 
If a time before the current time is given, the next day is used. Also make sure that "start_automatically" is set to true and that 
you entered your email and password.  
For example, if you want the script to start searching meetings at 6 in the morning on the next day, you would input `06:00` in the config.

- **start_automatically:**  
If true, skips the `Start [s], Reload teams [r], Quit [q]` dialog and starts on it's own. Useful if you schedule the script to start at a specific time.  

- **organisation_num:**     
If your Teams account is in multiple organisations, as seen in the example below, change the organisation_num to the number of the list item (counting starts from 1)  

- **random_delay:**  
If true, adds a random delay (10s-30s) before joining a meeting. Can be useful so the bot seems more "human like".  

- **check_interval:**  
The amount of seconds to wait before checking for meetings again. Only integer numbers greater than 1 are allowed.

- **auto_leave_after_min:**  
If set to a value greater than zero, the bot leaves every meeting after the specified time (in minutes). Useful if you know the length of your meeting, if this is left alone, by default the bot will stay in the meeting until a new one is available.

- **leave_if_last:**  
If true, leaves the meeting if you are the last person in it.

- **headless:**     
If true, runs Chrome in headless mode (does not open GUI window and runs in background).

- **mute_audio:**     
If true, mutes all the sounds.

- **chrome_type:**     
Valid options: `google-chrome`, `chromium`, `msedge`. By default, google chrome is used, but the script can also be used with Chromium or Microsoft Edge.


## Run the script  
  
 1. Rename the [config.json.example](config.json.example) file to "config.json"  
 2. Edit the "config.json" file to fit your preferences (optional)  
 3. Install Selenium and webdriver_manager
 4. Run [auto_joiner.py](auto_joiner.py): `python auto_joiner.py`  
 
