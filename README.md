Covid-19 dataflow using the Tweakstreet ETL tool (see: https://tweakstreet.io/).

The origin of the data used is: https://github.com/CSSEGISandData/COVID-19. This is the data repository for the 2019 Novel Coronavirus Visual Dashboard operated by the Johns Hopkins University Center for Systems Science and Engineering (JHU CSSE). The well-known dashboard is available here: https://www.arcgis.com/apps/opsdashboard/index.html#/bda7594740fd40299423467b48e9ecf6

The controlflow runs the dataflow and uses the data files to calculate:
  - the total number of cases (of type "confirmed" or of type "deaths")
  - the difference to the previous day (if any) total 
  - the difference in percent to the previous day (if any) total
  - the total number of cases compared to 100000 people of the countries population
  - the total number of cases compared to 100 people of the countries population

Two files are output:
  - a file containing the numbers per country
  - a file containing the numbers per continent
  
For each country or continent two lines per date (from the input file's name) are generated: one for confirmed cases and one for death cases.

Files are sorted by date (descending), type (confirmed or deaths, ascending) and country respectively continent (ascending).

Following steps to run the flow:
- install the Tweakstreet ETL tool from https://tweakstreet.io
- clone the GitHub repository of Johns Hopkins University: https://github.com/CSSEGISandData/COVID-19
- clone this repository: https://github.com/uwegeercken/covid19-dataflow-01
- open the controlflow "covid-controlflow.cfl" in the Tweakstreet tool
- in the controflow properties, adjust the path (root_folder_data variable) to the Johns Hopkins University data
- optionally, in the controlflow modify the "Find Files" step to use the desired list of files. per default all CSV files of year 2021 are used.
- run the flow

Note: the CSV output files are created in the folder where the flow is located. You can adjust the path in the dataflow CSV output steps.

last update: uwe.geercken@web.de - 2021-02-06
