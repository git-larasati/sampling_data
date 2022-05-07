# sampling_data
Pacmann - BI/DA Course (Batch 8) - Tugas 4

## EXPLANATION

- mandatory bin/bash:

`#!/bin/bash`

- if something fails, then abort shell:

`set -ex`

- download file from this link:

`curl -LJO https://github.com/labusiam/dataset/raw/main/weather_data.xlsx`

- install in2csv on Python to access CSV data from individual sheets in XLSX file:

`pip install csvkit`

- access CSV data from xlsx files, THEN save them as CSV format:

`in2csv weather_data.xlsx --sheet "weather_2014" > weather_2014.csv`

`in2csv weather_data.xlsx --sheet "weather_2015" > weather_2015.csv`


- combine CSV data #1 and CSV data #2, THEN save them as new CSV file:

`csvstack weather_2014.csv weather_2015.csv > weather.csv`

- remove original XLSX that was downloaded earlier: 

`rm weather_data.xlsx`

- install random sampling package from Python:

`pip install sample-stream`

- do random sampling with a rate of 0.3 from CSV file, THEN save it as a new CSV file:

`cat weather.csv | sample -r 0.3 > sample_weather.csv`
