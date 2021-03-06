# Changelog

All notable changes to the API will be documented here.

## 10-03-2021

**Breaking changes to the API.** Several fields will be made nullable on March 22, 2021. Two deprecated fields will be removed.

In the coming months, the Traffic Data API will be extended with historical data from the period 1996 - 2019. This dataset has slight differences compared to the traffic data that is currently available. Unfortunately, this requires making a few breaking changes to the GraphQL API. The API schema will be updated to reflect the below changes on the 22th of March, with historical aggregates becoming available gradually in the months following. Hour and day aggregates are due first, then average volumes.

### Nullable coverage

Coverage &mdash; a metric describing the quality and completeness of the traffic data aggregates &mdash; does not exist for the historical data from this period and will always be `null`. Therefore, a breaking schema change will be made where the `coverage` field is made nullable for all average types under `trafficData > volume > average`. This field is already nullable for hour and day aggregates.

### Nullable validSpeed and validLength

Similarly, the `validSpeed`, `validLength`, `validSpeedVolume` and `validLengthVolume` fields will be made nullable, as these were also not computed for the historical data. This affects all aggregates and averages, including hour and day aggregates.

### New length range class

The historical data has slightly different length ranges classes compared to the current data. The difference is in the upper range, where the historical data uses the length range class `[16.0, ...)`. The aggregates associated with this class are conceptually equal to the sum of the current `[16.0, 24.0)` and `[24.0, ...)` aggregates. The two latter classes are not present in the historical data. This change entails that the set of length range classes returned from the API can now be heterogenous: data for the historical period in time will use the old classes, while current traffic data will continue to use the same classes as before.

### Removing deprecated fields

The `validSpeedRatio` and `validLengthRatio` fields for hour and day aggregates have been deprecated for more than a year and will now be removed. Use of these fields should be replaced with `volumeNumbers > validSpeed` and `volumeNumbers > validLength`.

## 26-02-2021

Changes to the Trafikkdata API will be published here. In addition the changes will be availible on the Twitter account [@VegvesenData](https://twitter.com/vegvesendata).
