# Geospatial Time Series

Several extractors push data to the Clowder Geostreams API, which allows registration of data streams that accumulate
datapoints over time. These streams can then be queried, visualized and downloaded to get time series of various 
measurements across plots and sensors.

TERRA-REF organizes data into three levels:

* Location (e.g. plot, or a stationary sensor)
    * Information stream (a particular instrument's data, or a subset of one instrument's data)
        * Datapoint (a single observation from the information stream at a particular point in time)


### Sensor destinations

Here, the various streams that are used in the pipeline and their contents are listed.

* Location group
    * Stream name
        * **Datapoint property** [units / sample value]
        * ...

---

* Full Field (Environmental Logger)
    * Weather Observations
        * **sunDirection** [degrees / 358.4948271126]
        * **airPressure** [hPa / 1014.1764580218]
        * **brightness** [kilo Lux / 1.0607318339]
        * **relHumidity** [relHumPerCent / 19.3731498154]
        * **temperature** [DegCelsuis / 17.5243385113]
        * **windDirection** [degrees / 176.7864009522]
        * **precipitation** [mm/h / 0.0559327677]
        * **windVelocity** [m/s / 3.4772789697]
        * raw values shown here; check if extractor converts to SI units
    * Photosynthetically Active Radiation
        * **par** [umol/(m^2*s) / 0]
    * co2 Observations
        * **co2** [ppm / 493.4684409718]
    * Spectrometer Observations
        * **maxFixedIntensity** [16383]
        * **integration time in us** [5000]
        * **wavelength** [long array of decimals]
        * **spectrum** [long array of decimals]
        
* AZMET Maricopa Weather Station 
    * Weather Observations 
        * **wind_speed** [1.089077491]
        * **eastward_wind** [-0.365913231]
        * **northward_wind** [-0.9997966834]
        * **air_temperature** [Kelvin/301.1359779]
        * **relative_humidity** [60.41579336]
        * **preciptation_rate** [0]
        * **surface_downwelling_shortwave_flux_in_air** [43.60608856]
        * **surface_downwelling_photosynthetic_photon_flux_in_air** [152.1498155]
    * Irrigation Observations
        * **flow** [gallons / 7903]
    
* UIUC Energy Farm - CEN
* UIUC Energy Farm - NE
* UIUC Energy Farm - SE
    * Energy Farm Observations - CEN/NE/SE
        * **wind_speed**
        * **eastward_wind**
        * **northward_wind**
        * **air_temperature**
        * **relative_humidity**
        * **preciptation_rate**
        * **surface_downwelling_shortwave_flux_in_air**
        * **surface_downwelling_photosynthetic_photon_flux_in_air**
        * **air_pressure**
    
* PLOT_ID e.g. Range 51 Pass 2 (each plot gets a separate location group)
    * sensorName - Range 51 Pass 2 (each sensor gets a separate stream within the plot)
        * **fov** [polygon geometry]
        * **centroid** [point geometry]
    * canopycover - Range 51 Pass 2
        * **canopy_cover** [height/0.294124289126]
