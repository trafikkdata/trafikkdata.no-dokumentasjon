## Changelog

All notable changes to the API will be documented here.

### 17-09-2024

**Breaking changes to the API.** The fields `meteringDirectionChanged` have been removed from the API.

### 01-08-2024

No breaking changes, only deprecations.

#### Deprecated fields

The `meteringDirectionChanged` fields have been deprecated. Use of these fields should be replaced.

### 13-03-2024

As notified before, the enum value `OperationalStatus.TEMPORARILY_OUT_OF_SERVICE` has been replaced by `OperationalStatus.OUT_OF_SERVICE`.

### 08-03-2024

Notification about future change: On Wednesday, 13-03-2024, the enum value `OperationalStatus.TEMPRORARILY_OUT_OF_SERVICE` will be removed, and replaced by `OperationalStatus.OUT_OF_SERVICE`. The semantics of the new value is the same as the old one, so it is a drop-in replacement.

### 27-11-2023

Added field `volume.correctedStandardError` in the Trafikkdata API, which represents the standard error adjusted for the finite population correction (FPC). This correction is significant when a sample is a sizable fraction of the total population, which is often the case for average traffic counts. The corrected standard error is calculated by multiplying the standard error by the FPC factor. This adjustment yields a more precise estimation of the traffic sample mean's variability at the selected resolution.

The confidence interval in the API also utilizes the corrected standard error instead of the standard deviation, providing a more accurate range considering the finite population correction.


### 01-11-2023

The <a href="https://trafikkdata-api.atlas.vegvesen.no"  style="color: #44f55; text-decoration: underline;">Trafikkdata API</a> is now hosted on Atlas, and has been moved from <a href="https://www.vegvesen.no/trafikkdata/api"  style="color: #44f55; text-decoration: underline;">www.vegvesen.no/trafikkdata/api</a> to <a href="https://trafikkdata-api.atlas.vegvesen.no"  style="color: #44f55; text-decoration: underline;">trafikkdata-api.atlas.vegvesen.no</a>. 

Please use the new URL to access the **API**. The old URL is deprecated, and will no longer be available after **01.05.2024**.

### 19-09-2023

No breaking changes, only additions.

#### AdministrativeAreaHistory

Added field `Location.administrativeAreaHistory`. This shows the history of associated administrative areas (municipalities, counties, and country parts) that have been or are valid for this geographic location.

### 13-12-2022

No breaking changes, only additions and deprecations. The deprecated fields will be removed on 15.06.2023 at the earliest.

#### Lane numbers and traffic directions according to road link direction

Added field `Lane.laneNumberAccordingToRoadLink`. It is now possible to retrieve lanes numbered according to the road link direction. (Traffic in odd-numbered lanes travels with the road link direction, while traffic in even-numbered lanes travels against the road link direction.) This matches the lane numbers used by NVDB, and they do not change over time. `Lane.laneNumberAccordingToMetering` is still available as before, with lane numbers according to the road's current metering direction. `Lane.laneNumber`is now deprecated, as its meaning is ambiguous.

Similarly `Direction.fromAccordingToRoadLink` and `Direction.toAccordingToRoadLink` have been added, while `Direction.from` and `Direction.to` have been deprecated.

`TrafficRegistrationPoint.meteringDirectionChanged` has also been deprecated. It should not be relevant to API consumers anymore, thanks to the new fields described above.

### 10-03-2021

**Breaking changes to the API.** Several fields will be made nullable on March 22, 2021. Two deprecated fields will be removed.

In the coming months, the Traffic Data API will be extended with historical data from the period 1996 - 2019. This dataset has slight differences compared to the traffic data that is currently available. Unfortunately, this requires making a few breaking changes to the GraphQL API. The API schema will be updated to reflect the below changes on the 22th of March, with historical aggregates becoming available gradually in the months following. Hour and day aggregates are due first, then average volumes.

#### Nullable coverage

Coverage &mdash; a metric describing the quality and completeness of the traffic data aggregates &mdash; does not exist for the historical data from this period and will always be `null`. Therefore, a breaking schema change will be made where the `coverage` field is made nullable for all average types under `trafficData > volume > average`. This field is already nullable for hour and day aggregates.

#### Nullable validSpeed and validLength

Similarly, the `validSpeed`, `validLength`, `validSpeedVolume` and `validLengthVolume` fields will be made nullable, as these were also not computed for the historical data. This affects all aggregates and averages, including hour and day aggregates.

#### New length range class

The historical data has slightly different length ranges classes compared to the current data. The difference is in the upper range, where the historical data uses the length range class `[16.0, ...)`. The aggregates associated with this class are conceptually equal to the sum of the current `[16.0, 24.0)` and `[24.0, ...)` aggregates. The two latter classes are not present in the historical data. This change entails that the set of length range classes returned from the API can now be heterogenous: data for the historical period in time will use the old classes, while current traffic data will continue to use the same classes as before.

#### Removing deprecated fields

The `validSpeedRatio` and `validLengthRatio` fields for hour and day aggregates have been deprecated for more than a year and will now be removed. Use of these fields should be replaced with `volumeNumbers > validSpeed` and `volumeNumbers > validLength`.

### 26-02-2021

Changes to the Trafikkdata API will be published here. In addition the changes will be availible on the Twitter account <a href="https://twitter.com/vegvesendata"  style="color: #44f55; text-decoration: underline;">@VegvesenData.</a> 
