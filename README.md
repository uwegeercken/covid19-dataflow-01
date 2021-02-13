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
  
Files are sorted by date (descending), type (confirmed or deaths, ascending) and country respectively continent (ascending).

Following steps to run the flow using the Tweakstreet GUI:
- install the Tweakstreet ETL tool from https://tweakstreet.io
- clone the GitHub repository of Johns Hopkins University: https://github.com/CSSEGISandData/COVID-19
- clone this repository: https://github.com/uwegeercken/covid19-dataflow-01
- open the controlflow "covid-controlflow.cfl" in the Tweakstreet tool
- in the controlflow properties, adjust the path (root_folder_data parameter) to the Johns Hopkins University data
- optionally, in the controlflow properties, adjust the file_pattern_matcher parameter to use the desired list of files. Per default all CSV files of year 2021 are used.
- select "File" > "Choose Config Module" from the menu and select the relevant config-module file: DEV or PROD. The dev module simply does more logging.
- run the flow

Running the flow on the shell:
Instead of running the flow in the gui, it can also be run using the engine.sh (engine.bat) command line tool. It is located in the /bin folder of the Tweakstreet installation.

Start the command line tool like in the example below to run the flow and passing the two parameters ("-p" arguments) and the name of the config module ("-g" argument):

    Example: bin/engine.sh -g [path to the controlflow]/config-module-dev.tsm -p root_folder_data /[folder to the data files] -p file_match_pattern .*/01-[0-9]{2}-2021.csv [path to the controlflow]/covid-controlflow.cfl


Note: the CSV output files are created in the data/output folder. You can adjust the path in the dataflow CSV output steps.

last update: uwe.geercken@web.de - 2021-02-13
