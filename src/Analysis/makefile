DATA = ../../data
TEMP = ../../gen/temp
OUTPUT = = ../../gen/output

all: $(TEMP)/df_pivot.csv $(OUTPUT)/plot.pdf $(OUTPUT)/plot_all.pdf

$(TEMP)/df_pivot.csv: $(TEMP)/df_grouped.csv pivot_table.R
    mkdir -p ../../gen/output
    R --vanilla < pivot_table.R

$(OUTPUT)/plot.pdf: $(TEMP)/df_pivot.csv plot.R
    R --vanilla < plot.R

$(OUTPUT)/plot_all.pdf: $(TEMP)/df_grouped.csv plot_all.R
    R --vanilla < plot_all.R