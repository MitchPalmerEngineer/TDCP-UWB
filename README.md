# TDCP-UWB
Time-Differenced Carrier Phase (TDCP) and Ultra-wideband (UWB) integrated position solution dataset.
Collected on March 25, 2025 at University of Calgary by Mitch Palmer, M.Sc. Geomatics Engineer 

Phone observations collected using 2x Google Pixel 7 Pro (Android 15) HW Year: 2020 HW Model: Broadcom, BCM4776, GLL ver. 154.20.24 616640.
TDCP observations collected with Google GNSSLogger and processed with Google GNSSAnalysisTool (see https://developer.android.com/develop/sensors-and-location/sensors/gnss).
UWB observations collected using Android Jetpack Core Ultra-Wideband (see https://developer.android.com/jetpack/androidx/releases/core-uwb), custom application built with Android Studio.
Real-Time Kinematic (RTK) precise GNSS used to observe reference trajectories with 3x Trimble R10, continuous topographic RTK survey with base over known monument.

# Contents
data/tdcp_uwb_all_data.csv: comma-delimited "per-epoch" file containing all data
data/UWB-TDCP_Field_test.json: JSON-formatted "per-epoch" file containing all data

results/kml/...: KML shapefile containing per-test run positions of all types (RTK, ADR, PSR, TDCP-UWB)
results/stats/tdcp_uwb/...: statistical plots relating to the TDCP-UWB results
results/stats/uwb/...: statistical plots relating to the UWB observations

# all data
data in the above two files contains:
- UWB observed distance, relative azimuth, relative vertical angle
- RTK computed geometric distance, computed UWB distance accuracies
- RTK observed positions (lat, lon, hgt, N, E)
- smartphone rover 1&2 PSR & ADR observed positions (lat, lon, hgt, N, E) with accuracies
- TDCP-UWB computed positions (lat, lon, N, E) with accuracies, using ADR positions+UWB distance obs and one known control point (from RTK)

# notes
TDCP-UWB done in 2D frame because of 3D geometry datum defects when using UWB, and typical pedestrian use-case not requiring height information
4 individual test runs contained in the data, all labeled