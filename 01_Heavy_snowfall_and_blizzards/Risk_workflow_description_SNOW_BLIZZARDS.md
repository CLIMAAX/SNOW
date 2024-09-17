# Heavy snow and blizzards - workflow for risk assessment under climate change

This workflow is intended to aid the user in assessing the risks due to heavy snowfall and blizzards. The objective is to understand the probability of severe snowfall and blizzards under the present climate for European regions most impacted by this hazard. Additionally, we seek to investigate how climate change may change this hazard in the future.

## Hazard assessment under climate change

### Impact-based indicators

#### Blizzards
A blizzard is a severe storm condition defined by low temperature, sustained wind or frequent wind gusts, and considerable precipitating or blowing snow. To define blizzard conditions, we propose the use of the following impact indicator:

**Blizzard days** = Tmean  ≤ 0 °C **and** Rs ≥ 10 cm **and** Wg ≥ 17 m/s , 
where:
 - Tmean - mean daily temperature
 - Rs - amount of snow
 - Wg - wind gust velocity

This impact indicator was defined taking into account the exposure of critical infrastructure, i.e., roads, rails, power lines, and telecommunication to the hazard, and is based on an extensive literature review, media reports, surveys conducted with European CI operators and case studies ( Vajda et al., 2014).

#### Heavy snowfall

Heavy snowfall may cause many disruptions and impacts in various sectors; however, the impacts and consequences of this hazard depend on the affected sector, infrastructure, and also preparedness of society which varies over Europe.  For example, already a few centimeters of snow can disrupt road traffic, but doesn’t normally cause any harm to energy infrastructure. Many weather services have three warning levels based on the severity of expected impacts, which are typically different for different sectors of infrastructure. There is a large variation in the national warning criteria or thresholds.

Similarly to blizzards, the impact indicators for heavy snowfall were defined taking into account the exposure of critical infrastructure, i.e., roads, rails, power lines, and telecommunication to the hazard, and is based on an extensive literature review, media reports, surveys conducted with European CI operators and case studies. The qualitative description of the two-level thresholds for daily snowfall amounts are:

**1st threshold ( > 6 cm):** Some adverse impacts are expected, their severity depends on the resilience of the system, and transportation is mainly affected.

**2nd threshold ( > 25 cm):**  The weather phenomena are so severe that is likely that adverse impact will occur, CI system will be seriously impacted.

### Assessing the hazard - annual probability

This workflow calculates the Annual probability (%) of a blizzard and heavy snowfall days during the specified period for the region of interest.


The annual probability is determined by dividing the count of events surpassing predefined thresholds within a year by the total number of days in that year. The result is then multiplied by 100 to express the probability as a percentage:

    P = ((variable > threshold) / days in year ) X 100

##  Datasets used

We computed the impact-based indices for heavy snowfall and blizzards using the ERA5 and EURO-CORDEX datasets, which were acquired through the CDS API sourced from the Copernicus Climate Data Store.

- ERA5 single-level dataset: available from the  [Climate data store](https://cds-beta.climate.copernicus.eu/datasets/reanalysis-era5-single-levels?tab=overview)

- CORDEX single-level dataset: available from the  [Climate data store](https://cds-beta.climate.copernicus.eu/datasets/projections-cordex-domains-single-levels?tab=overview)

### Limitations

While ERA5 and EURO-CORDEX are valuable datasets for assessing snow and blizzard events, limitations in spatial resolution, representation of extremes, and model uncertainties necessitate the use of local observations and additional high-resolution simulations for accurate snowstorm risk assessment. Applying bias correction techniques and using multi-model ensembles can help mitigate some of these uncertainties.

## Risk assessment methodology

In this workflow, risk is determined as a combination of the probability of occurrence of heavy snow or blizzards (hazard) with population density (exposure). The risk can be assessed for both present and future climate conditions by using the hazard impact-based indicators derived based on climate models. 

The method for assessing risk involves visually representing the susceptible population exposed to intense snowfall and blizzards. This can be achieved by overlaying the impact-based indicators for heavy snowfall and blizzards with population data. 

### Exposure - population density
For assessing population exposure, we relied on the JRC data portal, particularly the Global Human Settlement Layer (GHSL)

As there is no API available for downloading population data, we can utilize the Pooch library to download and unzip it.

The population data are available from the  [JRC data portal](https://ghsl.jrc.ec.europa.eu/download.php?ds=pop).

## Structure of the workflow
This workflow consists of two scripts, where the user is guided in performing a hazard and risk assessment for heavy snowfall and blizzards. 

In the next pages you will find:
1. Hazard assessment for heavy snowfall and blizzards ([link to notebook on GitHub](https://github.com/CLIMAAX/SNOW/blob/main/01_Heavy_snowfall_and_blizzards/Hazard_assessment_SNOW_BLIZZARDS.ipynb))
2. Risk assessment using hazard impact indicators and population exposure data ([link to notebook on GitHub](https://github.com/CLIMAAX/SNOW/blob/main/01_Heavy_snowfall_and_blizzards/Risk_assessment_SNOW_BLIZZARDS.ipynb))

## Outputs of the workflow

![Annual probability (%) of blizzard during the period 1981-2010 based on ERA-Interim data. (Groenemeijer P. et al. 2016)]

![Picture 1](https://github.com/user-attachments/assets/901ca9a7-f9b4-4410-970f-0c0364eafb89)



![Multi-model mean change in annual probability of blizzards (in percentage points) by 2071-2100 under the RCP 8.5 scenario; white dots denote significant change at the 95% level of confidence. (Groenemeijer P. et al. 2016)]

![Picture 2](https://github.com/user-attachments/assets/cc58be2d-9865-4e2e-b812-a3be940ac3ff)




## Authors

This workflow was developed by the Finnish Meteorological Institute.

## References
Groenemeijer P., Vajda A., Lehtonen I., Kämäräinen M., Venäläinen A., Gregow H., Becker N., Nissen K., Ulbrich U., Morales Nápoles O., Paprotny D., Púčik T., 2016: Present and future probability of meteorological and hydrological hazards in Europe, EU RAIN Deliverable 2.5, http://rain-project.eu/wp-content/uploads/2016/09/D2.5_REPORT_final.pdf 






