LATEXMK ?= latexmk
MAIN := main.tex
OUTDIR := output/pdf

.PHONY: all clean

all:
	mkdir -p $(OUTDIR)
	$(LATEXMK) -pdf -interaction=nonstopmode -halt-on-error -outdir=$(OUTDIR) $(MAIN)

clean:
	$(LATEXMK) -C -outdir=$(OUTDIR) $(MAIN)
