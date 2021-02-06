Covid-19 dataflow using the Tweakstreet ETL tool (see: https://tweakstreet.io/).

The origin of the data used is: https://github.com/CSSEGISandData/COVID-19. This is the data repository for the 2019 Novel Coronavirus Visual Dashboard operated by the Johns Hopkins University Center for Systems Science and Engineering (JHU CSSE). The well-known dashboard is available here: https://www.arcgis.com/apps/opsdashboard/index.html#/bda7594740fd40299423467b48e9ecf6

The controlflow runs the dataflow and uses the data files to calculate the number of Covid-19 confirmed and death cases related to the population of the country and continent. In the control flow the files are collected using a regular expression.

Following steps:

- install the Tweakstreet ETL tool from https://tweakstreet.io
- clone the GitHub repository of Johns Hopkins University: https://github.com/CSSEGISandData/COVID-19
- clone this repository: https://github.com/uwegeercken/covid19-dataflow-01
- open the controlflow "covid-controlflow.cfl" in the Tweakstreet tool
- in the controflow properties, adjust the path (root_folder_data variable) to the Johns Hopkins University data
- run the flow

last update: uwe.geercken@web.de - 2021-02-06
