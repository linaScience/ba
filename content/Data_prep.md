# Data preprocessing

    - we need to generate our own time series in order to use lstm

    - remove unnecessary rows 
      - meaning we only need TYPE_WAYPOINT, TYPE_WIFI and TYPE_ACCELEROMETER
    - we need data for every timestamp of wifi data
      - we could either:
        - calculate the total acceleration and the velocity for each timestamp
        - interpolate the waypoint for the wifi times in order to have a time series for the wifi data with waypoints
          - possible improvement: acceleration could make interpolation more precise

    - we want to predict to which AP we are going to move towards
        - therefore, we only need bssid
            - with ssids we could make this more complex and complicated, but also possible
            - remove bssid
        - make encoding (we first want the best bssid to be among the 3 best predictions)
    
    - maybe we need to filter out sites with too less waypoints
    - train/test/validation (80/10/10)
    - do we aggregate for each floor?
    - we want to guess if a certain bssid is among the top 3 bssids (according to the rssi)
      - we want to further improve the guess: the best, the 2 best and 3 best among these 3 bssids
