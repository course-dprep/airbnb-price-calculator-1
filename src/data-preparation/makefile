DATA = ../../data
EXPLORATION = ../../src/data-preparation

all: $(DATA)/listings_download.csv $(DATA)/listings_final.csv $(EXPLORATION)/data_exploration.pdf

## download & merge the data
$(DATA)/listings_download.csv: download_merge_data.R
	R --vanilla < download_merge_data.R

## clean the data
$(DATA)/listings_final.csv: cleaning_data.R
	R --vanilla < cleaning_data.R

## explore the data
$(EXPLORATION)/data_exploration.pdf: data_exploration.Rmd
	Rscript -e 'rmarkdown::render("data_exploration.Rmd")'
