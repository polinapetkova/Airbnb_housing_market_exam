DATA = ../../data
TEMP = ../../gen/temp

all: $(DATA)/listings.csv $(DATA)/reviews.csv $(TEMP)/df_merged.csv $(TEMP)/df_grouped.csv

../../data/reviews.csv: download.R
    R --vanilla < download.R

../../data/listings.csv: download.R
    mkdir -p ../../data
    R --vanilla < download.R

../../gen/temp/df_merged.csv: ../../data/listings.csv ../../data/reviews.csv  clean.R
    mkdir -p ../../gen/temp
    R --vanilla < clean.R

../../gen/temp/df_grouped.csv: ../../data/listings.csv ../../data/reviews.csv ../../gen/temp/df_merged.csv: clean.R
    R --vanilla < clean.R