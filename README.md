# airbnb prices across european cities

Code and final report for a multilevel analysis of Airbnb nightly prices in
seven European cities. The models combine listing characteristics,
neighbourhood-level context, and tourist amenities from OpenStreetMap.

## files

- `airbnb_multilevel_analysis.Rmd` — data preparation, spatial joins, models,
  diagnostics, and figures.
- `Multilevel_Analysis_Final_Project_Jane_Shadrina.pdf` — final report.

## data

The raw data are not included in this repository. Set `AIRBNB_DATA_DIR` to a
directory containing listing and neighbourhood files for Amsterdam, Berlin,
London, Madrid, Rome, Venice, and Vienna (get it here https://insideairbnb.com/get-the-data/):

```text
listings_<city>.csv.gz
neighbourhoods_<city>.geojson
```

Tourist amenities are downloaded from OpenStreetMap and cached locally in
`outputs/osm_cache`.

## run

Install the packages listed in the R Markdown setup section, then render the
analysis from the project directory:

```sh
AIRBNB_DATA_DIR=/path/to/data Rscript -e \
  'rmarkdown::render("airbnb_multilevel_analysis.Rmd")'
```

Generated tables, model objects, intermediate data, and figures are written to
`outputs/`. This directory is excluded from version control.
