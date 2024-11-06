# ITC Seismology 2024 - Waveform based detection and location

## Lecturers

* Simone Cesca <cesca@gfz-potsdam.de>
* Pinar Büyükakpinar <pinar@gfz-potsdam.de>


## Chat

Please join the [itc-qseek channel]([https://hive.pyrocko.org/pyrocko-support/channels/itc2024) on the
[Pyrocko Hive](https://hive.pyrocko.org).

## Program

Thursday, November 7

	08:30 - 10:00: Waveform based detection and location (Simone Cesca)
	10:30 - 12:00: Waveform based seismic catalog generation practical (Pinar Büyükakpinar)

Exercise dataset (Qseek)

## Links and Tutorials

* [Pyrocko web page](https://pyrocko.org)
* [Pyrocko manual](https://pyrocko.org/docs/current/)
* [Snuffler manual (Data Access, Preparation and Visualization)](https://pyrocko.org/docs/current/apps/snuffler/index.html)
* [Squirrel command line tool tutorial (Data Access, Preparation and Visualization)](https://pyrocko.org/docs/current/apps/squirrel/tutorial.html)

## Task

We will detect and locate earthquakes around Ataturk Dam using different distance weights

## Data

Dataset can be downloaded via the link: https://nextcloud.gfz-potsdam.de/s/HrsrTTMpQgPP5Yn

## Distance Weights Calculation

The `DistanceWeights` class is designed to compute weights based on the distance from a set of stations to a series of nodes in a spatial context. The weights are calculated using two different methods depending on the configuration:

**Exponential Decay Function:**
   The weights are calculated using the following formula:

   $$ w = e^{-\left(\frac{d^p}{r^p}\right)} $$

   where:
   - \( w \) is the weight.
   - \( d \) is the distance from the station to the node.
   - \( r \) is the cutoff distance (in meters).
   - \( p \) is the exponent of the spatial decay function (default is 3.0).

   This method provides a weight that decreases exponentially with distance.

# Parameters
- **Exponent (`exponent`)**: The exponent of the spatial decay function (default is 3.0).
- **Cutoff Distance (`radius_meters`)**: The cutoff distance for the spatial decay function in meters (default is 8000.0).
- **LRU Cache Size (`lut_cache_size`)**: Size of the LRU cache in bytes (default is 200 MB).

## Configuration

Edit the test.json and change the parameters

## Running qseek

Start the earthquake detection with `qseek search test.json`

## Visualize results

`qseek snuffler test`

## Citation

Please cite Qseek as:

> Marius Paul Isken, Peter Niemz, Jannes Münchmeyer, Sebastian Heimann, Simone Cesca, Torsten Dahm, Qseek: A data-driven Framework for Machine-Learning Earthquake Detection, Localization and Characterization, Seismica, 2024, *submitted*
