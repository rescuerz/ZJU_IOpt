#
# Makefile for LaTeX files
#
LATEX	= xelatex
BIBTEX	= bibtex
PDF2PS	= pdf2ps

SRC = main.tex
SUB = $(shell ls -d * | grep chp)

#
# If only one level directory, you can using:
# FIL = $(shell ls *.tex)
# Or only sub dir (frame untouched):
# FIL = $(shell find $(SUB) -name  '*.tex')
#
FIL = $(shell find . -name  '*.tex')
BIB = $(shell find . -name  '*.bib')
PDF = $(SRC:%.tex=%.pdf)
PSF = $(SRC:%.tex=%.ps)
AUX = $(SRC:%.tex=%.aux)
TRG = $(PDF)

all	: $(TRG)

pdf	: $(TRG)

$(TRG)	: $(FIL) $(BIB)
	$(LATEX) $(SRC)
	$(BIBTEX) $(AUX)
	$(LATEX) $(SRC)
	$(LATEX) $(SRC)

$(PSF)	: $(PDF)
	$(PDF2PS) $(PDF)

.PHONY	: all show clean ps pdf showps veryclean
clean	:
	  -rm -f *.out *.log *.aux *.dvi *.bbl *.blg *.ilg *.toc *.lof *.lot *.idx *.ind  *.gz *~  
veryclean	:
	  -rm -f *.bak *.backup *.out *.ps *.pdf *.log *.aux *.dvi *.bbl *.blg *.ilg *.toc *.lof *.lot *.idx *.ind *.ps  *.gz *~
