# Energy Price Analysis

The goal of this repository is to analyze possible contributing factors to the energy price
hike which could be observed in the autumn and winter months of 2021. Of course, there are
many factors and it is impossible for me to inspect all of them in a single analysis. This
work in particular focuses on visualizing the general trend in energy capacity, energy production,
and specific events that could lead to such a drastic development. The events in question are:

- The possibility of "wind-draughts" leading to a significant decrease in energy production in
  regions that have a high percentage of on-grid wind capacity
- The influence of politically motivated price squeezes in the natural gas sector.

## Data Sources

I base my analysis on multiple data sources. All of them are freely available and open for
academic use. I am aware that there is some uncertainty in the data as the data sets include
models as well as self-reports. At least for the inspected regions of interests in Europe
there is the benefit of a rather well developed reporting infrastructure.

### International Renewable Energy Agency

The [IRENASTAT](http://pxweb.irena.org/pxweb/en/IRENASTAT) online tool offers data regarding

- on-grid energy capacity by country year and technology
- off-grid energy capacity by country year and technology
- on-grid energy production by country year and technology
- off-grid energy production by country year and technology

The agency offers data for all countries worldwide but I suspect that for under-serviced
regions the disparity between factual values and reported values might be quite striking.
For Europe I assume that the data is at least reliable enough for this analysis. I chose to
include this data in particular because it is one of the few sources which has a granular
depiction of energy capacity.

### Our World in Data - Energy

The [OWID Energy Explorer](https://ourworldindata.org/energy) is a data aggregation platform
that focuses especially on changes in statistics related to energy. It is additionally enriched
with additional information like carbon intensity, energy mix and GDP which makes it a powerful
tool. The coverage is world wide. The data set is regularly updated but the the update intervals
are irregular.

### European Centre for Medium-Range Weather Forecasts Reanalysis v5

The ERA5 data set is a global hourly gridded data set containing climate data like temperature,
precipitation and wind speeds. It is freely available both from the
[Copernicus Climate Data Platform](https://climate.copernicus.eu/climate-reanalysis) as well as
the [AWS Open Data Repository](https://registry.opendata.aws/ecmwf-era5/).

### European Network of Transmission System Operators for Electricity Transparency Platform

The ENTSO-E Transparency Platform includes 42 electricity transmission system operators (TSOs)
from 35 European countries and offers hourly data regarding transmission, day-ahead-pricing, generation,
load, generation, and balancing. It is one of the richest and most granular data sources for the
TSOs that regularly report their data. Unfortunately, that is not the case for some TSOs.

## Data Limitations

As mentioned before the included data sources don't have the same geographic and/or temporal resolution.
The update frequency for most of the used data sources is very serviceable but there can be delays for
rather recent dates.

Additionally, there is data available behind paywalls that would have been very useful in this analysis.
The most interesting sources would be:

- [European Energy Exchange Data](https://www.powernext.com/spot-market-data) (particularly Spot Market prices)
  as those price time series are very sensitive to changes in supply and demand
- [Electricity Map Historic and Realtime Data](https://electricitymap.org/) includes data that not only looks
  at primary energy consumption but rather the energy mix of the actual energy consumption and its CO2
  intensity corrected for trading/transmission behavior and outsourced industrial production in relation
  to national consumption.

## Assumptions

The notebooks in this repository assume that they are run on the [Pangeo](https://pangeo.io/) environment in
at [HAKOM Time Series GmbH](https://www.hakom.at/). At some times some calls to AWS S3 compatible storage providers
might be targeting a local resource which is not available outside. If you are interested in the environment and
its differences to a public Pangeo instance you can read
[this blog post](http://big-data-processing.pages.web.fh-kufstein.ac.at/gitbook/beyerle/build_your_own_pangeo.html).
The resulting artifacts of this work should have no assumptions on resources that are not available to everyone.

## Current State

I am currently still evaluating the data sources and building visualizations for my analysis. Currently all work is
done in the `notebooks` folder.
