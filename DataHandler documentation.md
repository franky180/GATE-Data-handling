DataHandler handels data for Monte-Carlo simulations with [[openGate]]

# Usage:
The root folder is called *master*. Within it, there is a folder *analyze* which contains the 
```python
dh = a.DataHandler(data, backgrounds, path_measurements = "measurements/", path_simulations = "simulations/")
```



## Background
A BackgroundObject should be of the form:
```python
LEHR = a.BackgroundObject(file_name = "*.xml", measurement_time = 300)
```
Where __file_name__ is the name of the file stored in *path_measurements* and __measurement_time__ is the measurement time in s.

## Data object
A data object should be of the form:
```python
# DataObject
d = a.DataObject(
        time=,
        activity=,
        file_mst="",
        top_distance=,
        top_file_sim="",
        bottom_distance=,
        bottom_file_sim="",
        scale_factor = 
    )

```

# Functions

## Get simulation
Usage:
```python
get_simulation(f, bg_name="background", measurement_time = 60)
 
```


## Get spectrum
Usage:
```python
get_spectrum(self, detector="both", data_name="Tc99m cubic", bg_cleared = False, normalized = False)
 
```

## Get positions
Usage:
```python
get_positions(self, detector="both", data_name="spectrum")
 
```

## Get peak area
Usage:
```python
get_peak_area(self, spectrum, plot=True, peak_channel=140, method="half-width", function="trapezoid")
 
```

Options for __method__:
- half-width: Represents FWHM
- 2half-width: Represents 2$\times$ FWHM
- full-peak: Represents the full peak which has to be hard coded (not implemented correctly yet)

Options for __function__:
- trapezoid: Linear connection between the points
- sigmoid: Sigmoidal connection between the points
- fit: Curve fit (not implemented correctly yet)


# Plot
- [[plot_]]