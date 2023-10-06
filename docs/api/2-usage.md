## Usage

The Traffic Data API is located at [https://www.vegvesen.no/trafikkdata/api](https://www.vegvesen.no/trafikkdata/api).

The API uses GraphQL, which is a data query language for APIs.
It defines a schema composed of different types and fields on those types.
It allows for introspection of the API and for creating strongly typed clients.
For more general information on GraphQL, visit [graphql.org/learn](https://graphql.org/learn/).

When opened in a web browser, the API is presented through GraphiQL, a graphical user interface for writing and executing queries.
Queries can also be performed programatically from a wide range of programming languages.
For more information, visit [graphql.org/code](https://graphql.org/code/).

In the following, we present a few examples of API queries.
For full documentation of all available queries and fields, use the [GraphiQL interface](https://www.vegvesen.no/trafikkdata/api) and click on `Docs`.

### Traffic registration points

A traffic registration point is a location on the road where traffic is registered. For more information, see [Om trafikkdata](../about/1-om-trafikkdata.md).
The `trafficRegistrationPoints` query allows users to list traffic registration points that satisfy certain criteria.

The following example lists all traffic registration points on European routes, with traffic registration point ID, name and coordinates (WGS-84).

```graphql
{
  trafficRegistrationPoints(searchQuery: { roadCategoryIds: [E] }) {
    id
    name
    location {
      coordinates {
        latLon {
          lat
          lon
        }
      }
    }
  }
}
```

[Open query in GraphiQL](<https://www.vegvesen.no/trafikkdata/api/?query=%7B%0A%20%20trafficRegistrationPoints(searchQuery%3A%20%7BroadCategoryIds%3A%20%5BE%5D%7D)%20%7B%0A%20%20%20%20id%0A%20%20%20%20name%0A%20%20%20%20location%20%7B%0A%20%20%20%20%20%20coordinates%20%7B%0A%20%20%20%20%20%20%20%20latLon%20%7B%0A%20%20%20%20%20%20%20%20%20%20lat%0A%20%20%20%20%20%20%20%20%20%20lon%0A%20%20%20%20%20%20%20%20%7D%0A%20%20%20%20%20%20%7D%0A%20%20%20%20%7D%0A%20%20%7D%0A%7D>).

### Traffic volume

Traffic volume for a given traffic registration point can be retrieved using the `trafficData` query.

#### Hourly traffic volume

The following example retrieves hourly traffic volume for two hours for the traffic registration point with ID `44656V72812`.

```graphql
{
  trafficData(trafficRegistrationPointId: "44656V72812") {
    volume {
      byHour(
        from: "2019-10-24T12:00:00+02:00"
        to: "2019-10-24T14:00:00+02:00"
      ) {
        edges {
          node {
            from
            to
            total {
              volumeNumbers {
                volume
              }
              coverage {
                percentage
              }
            }
          }
        }
      }
    }
  }
}
```

[Open query in GraphiQL](<https://www.vegvesen.no/trafikkdata/api/?query=%7B%0A%20%20trafficData(trafficRegistrationPointId%3A%20%2244656V72812%22)%20%7B%0A%20%20%20%20volume%20%7B%0A%20%20%20%20%20%20byHour(from%3A%20%222019-10-24T12%3A00%3A00%2B02%3A00%22%2C%20to%3A%20%222019-10-24T14%3A00%3A00%2B02%3A00%22)%20%7B%0A%20%20%20%20%20%20%20%20edges%20%7B%0A%20%20%20%20%20%20%20%20%20%20node%20%7B%0A%20%20%20%20%20%20%20%20%20%20%20%20from%0A%20%20%20%20%20%20%20%20%20%20%20%20to%0A%20%20%20%20%20%20%20%20%20%20%20%20total%20%7B%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20volumeNumbers%20%7B%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20volume%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%7D%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20coverage%20%7B%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20percentage%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%7D%0A%20%20%20%20%20%20%20%20%20%20%20%20%7D%0A%20%20%20%20%20%20%20%20%20%20%7D%0A%20%20%20%20%20%20%20%20%7D%0A%20%20%20%20%20%20%7D%0A%20%20%20%20%7D%0A%20%20%7D%0A%7D>)
The hourly and daily traffic volume (`byHour` and `byDay`) queries use pagination to split the data into pages, so that clients can process smaller chunks (maximum 100 hours/days) of data at a time.
To retrieve the next page, use the `cursor` value from the last `node` on the current page as the `after` argument in the next query.

#### Average daily traffic volume per year (ÅDT)

The following example retrieves average daily traffic volume per year for the traffic registration point with ID `44656V72812`.

```graphql
{
  trafficData(trafficRegistrationPointId: "44656V72812") {
    volume {
      average {
        daily {
          byYear {
            year
            total {
              volume {
                average
                confidenceInterval {
                  lowerBound
                  upperBound
                }
              }
              coverage {
                percentage
              }
            }
          }
        }
      }
    }
  }
}
```

[Open query in GraphiQL](<https://www.vegvesen.no/trafikkdata/api/?query=%7B%0A%20%20trafficData(trafficRegistrationPointId%3A%20%2244656V72812%22)%20%7B%0A%20%20%20%20volume%20%7B%0A%20%20%20%20%20%20average%20%7B%0A%20%20%20%20%20%20%20%20daily%20%7B%0A%20%20%20%20%20%20%20%20%20%20byYear%20%7B%0A%20%20%20%20%20%20%20%20%20%20%20%20year%0A%20%20%20%20%20%20%20%20%20%20%20%20total%20%7B%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20volume%20%7B%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20average%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20confidenceInterval%20%7B%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20lowerBound%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20upperBound%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%7D%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%7D%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20coverage%20%7B%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20percentage%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%7D%0A%20%20%20%20%20%20%20%20%20%20%20%20%7D%0A%20%20%20%20%20%20%20%20%20%20%7D%0A%20%20%20%20%20%20%20%20%7D%0A%20%20%20%20%20%20%7D%0A%20%20%20%20%7D%0A%20%20%7D%0A%7D>).

#### Traffic volume indices

A traffic volume index is a measure of how much traffic has increased or decreased from one year to the next.
The `trafficVolumeIndices` query returns indices for traffic registration points for a given month.
The `publishedTrafficVolumeIndices` query lists all the officially published traffic volume indices, which are indices that have been composed and verified by the Norwegian Public Roads Administration.
The IDs for these indices are used in the `publishedTrafficVolumeIndex` query, which returns an official traffic volume index for various areas for a whole year or a given month.
The response contains the traffic registration points that make up each index, as well as indices for administrative areas like counties, country parts and the whole country.

The following query returns the traffic volume percentage change from 2018 to 2019 for the whole country,
where `962` is the current ID of Vegtrafikkindeksen, which encompasses the whole country.

```graphql
{
  publishedAreaTrafficVolumeIndex(id: 962, year: 2019, month: 12) {
    aggregatedTrafficVolumeIndex(areaTypes: [COUNTRY]) {
      byRoadCategoryCombination {
        roadCategoryCombination
        last12MonthsIndicesByDayType {
          dayType
          byLengthRange {
            lengthRange {
              representation
            }
            volumeIndexNumber {
              percentageChange
            }
          }
        }
      }
    }
  }
}
```

[Open query in GraphiQL](<https://www.vegvesen.no/trafikkdata/api/?query=%7B%0A%09publishedAreaTrafficVolumeIndex(id%3A%20962%2C%20year%3A%202019%2C%20month%3A%2012)%20%7B%0A%20%20%20%20aggregatedTrafficVolumeIndex(areaTypes%3A%20%5BCOUNTRY%5D)%20%7B%0A%20%20%20%20%20%20byRoadCategoryCombination%20%7B%0A%20%20%20%20%20%20%20%20roadCategoryCombination%0A%20%20%20%20%20%20%20%20last12MonthsIndicesByDayType%20%7B%0A%20%20%20%20%20%20%20%20%20%20dayType%0A%20%20%20%20%20%20%20%20%20%20byLengthRange%20%7B%0A%20%20%20%20%20%20%20%20%20%20%20%20lengthRange%20%7B%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20representation%0A%20%20%20%20%20%20%20%20%20%20%20%20%7D%0A%20%20%20%20%20%20%20%20%20%20%20%20volumeIndexNumber%20%7B%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20percentageChange%0A%20%20%20%20%20%20%20%20%20%20%20%20%7D%0A%20%20%20%20%20%20%20%20%20%20%7D%0A%20%20%20%20%20%20%20%20%7D%0A%20%20%20%20%20%20%7D%0A%20%20%20%20%7D%0A%20%20%7D%0A%7D%0A>)

#### Other queries

The API can also provide traffic data for average daily traffic volume for months and seasons, as well as traffic volume per day.

### Examples

Usage examples from different languages that query the API for all traffic registration points on county roads.

#### JavaScript

Example of using the API from javascript:

```javascript
fetch("https://www.vegvesen.no/trafikkdata/api/", {
  method: "POST",
  headers: { "content-type": "application/json" },
  body: JSON.stringify({
    query: `{
      trafficRegistrationPoints(searchQuery: {roadCategoryIds: [F] }) {
        id
        name
        location {
          coordinates {
            latLon {
              lat
              lon
            }
          }
        }
      }
    }`
  })
})
  .then(res => res.json())
  .then(res => console.log(res))
  .catch(err => console.error(err));
```

#### curl

Example of using the API from `curl`:

```shell
curl 'https://www.vegvesen.no/trafikkdata/api/' \
  -X POST \
  -H 'content-type: application/json' \
  --data '{ "query": "{ trafficRegistrationPoints(searchQuery: {roadCategoryIds: [F] }) { id name location { coordinates { latLon { lat lon } } } } }", "variables": null}'
```
