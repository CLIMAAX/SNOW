# Snow workflow


## Risk assessment methodology

The method involves visually representing the susceptible population exposed to intense snowfall and blizzards. This can be achieved by overlaying indicators for heavy snowfall and blizzards (e.g. based on ERA5/CORDEX) with population data. The objective is to understand the present probability of severe snowfall and blizzards, pinpointing the regions most impacted within Europe. Additionally, we seek to investigate how climate change may modify this exposure over time.


## Hazard assessment

### Blizzard

A blizzard is a severe storm condition defined by low temperature, sustained wind or frequent wind gusts, and considerable precipitating or blowing snow. For blizzard conditions, we propose the use of the following impact indicator:

**Blizzard days** = Tmean  ≤ 0 °C, Rs (snow amount) ≥ 10 cm and Wg (wind gust) ≥ 17 m/s ( Vajda et al., 2014).

This impact indicator was defined taking into account the exposure of critical infrastructure, i.e., roads, rails, power lines, and telecommunication to the hazard, and is based on an extensive literature review, media reports, surveys conducted with European CI operators and case studies.


### Heavy Snow

Heavy snowfall may cause many disruptions and impacts in various sectors; however, the impacts and consequences of this hazard depend on the affected sector, infrastructure, and also preparedness of society which varies over Europe.  For example, already a few centimeters of snow can disrupt road traffic, but doesn’t normally cause any harm to energy infrastructure. Many weather services have three warning levels based on the severity of expected impacts, which are typically different for different sectors of infrastructure. There is a large variation in the national warning criteria or thresholds.

Similarly to blizzards, the impact indicators for heavy snowfall were defined taking into account the exposure of critical infrastructure, i.e., roads, rails, power lines, and telecommunication to the hazard, and is based on an extensive literature review, media reports, surveys conducted with European CI operators and case studies. The qualitative description of the two-level thresholds are:

**1st threshold ( > 6 cm):** Some adverse impacts are expected, their severity depends on the resilience of the system, and transportation is mainly affected.

**2nd threshold ( > 25 cm):**  The weather phenomena are so severe that is likely that adverse impact will occur, CI system will be seriously impacted.

This code calculates the Annual probability (%) of a blizzard and heavy snowfall days during the specified period and a region of interest.


**The annual probability**

The annual probability is determined by dividing the count of events surpassing predefined thresholds within a year by the total number of days in that year. The result is then multiplied by 100 to express the probability as a percentage

    P = ((variable > threshold) / days in year ) X 100

We computed indices for intense snowfall and blizzards using the ERA5 and CORDEX datasets, which were acquired through the CDS API sourced from the Copernicus Climate Data Store.

As there is no API available for downloading population data, we can utilize the Pooch library to download and unzip it.

- ERA5 single-level dataset: available from the  [Climate data store](https://cds-beta.climate.copernicus.eu/datasets/reanalysis-era5-single-levels?tab=overview)

- CORDEX single-level dataset: available from the  [Climate data store](https://cds-beta.climate.copernicus.eu/datasets/projections-cordex-domains-single-levels?tab=overview)


## Exposure assessment

For assessing population exposure, we relied on the JRC data portal, particularly the Global Human Settlement Layer (GHSL)

The population data are available from the  [JRC data portal](https://ghsl.jrc.ec.europa.eu/download.php?ds=pop)






