Covid-19 dataflow using the Tweakstreet ETL tool (see: https://tweakstreet.io/).

The origin of the data used is: https://github.com/CSSEGISandData/COVID-19. This is the data repository for the 2019 Novel Coronavirus Visual Dashboard operated by the Johns Hopkins University Center for Systems Science and Engineering (JHU CSSE). The well-known dashboard is available here: https://www.arcgis.com/apps/opsdashboard/index.html#/bda7594740fd40299423467b48e9ecf6

The dataflow uses the data to calculate the number of Covid-19 confirmed and death cases related to the population of the country and continent for a specific day. Per default the numbers are calculated for the previous day (today -1).

If you want to use the dataflow, do the following:

- install the Tweakstreet ETL tool from https://tweakstreet.io
- clone the GitHub repository of Johns Hopkins University
- clone this repository
- open the dataflow "covid-01.dfl" in the Tweakstreet tool
- adjust the path to the Johns Hopkins University data in the dataflow properties
- run the flow

Note: I have not (yet) created a dataflow which also shows the numbers over time.

last update: uwe.geercken@web.de - 2021-02-03
