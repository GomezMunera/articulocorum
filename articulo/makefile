# Makefile for LaTex compile
# Author: John Anderson Gómez Múnera
# cleaning extensions for other tex related

# Name of the TEX file to work with
FILE_TEX=digital

# Date style
DATESTYLE=`date +'%Y-%m-%d'`

all: pdflatex

pdflatex: clean	
	pdflatex ${FILE_TEX}.tex
	bibtex ${FILE_TEX}
	pdflatex ${FILE_TEX}.tex
	pdflatex ${FILE_TEX}.tex
	# Backup tex, bib and generated pdf files
	# There is one backup per day
	mkdir -p linea-tiempo/${DATESTYLE}
	cp ${FILE_TEX}.pdf linea-tiempo/${DATESTYLE}/${FILE_TEX}.pdf

view:
	# Open the pdf document with evince
	evince ${FILE_TEX}.pdf &

clean:
	# Cleaning other tex related files if applicable...
	rm -fv *log *aux *dvi *lof *lot *bit *idx *glo *bbl *ilg *toc *ind *blg *out *nlo *brf *nls *synctex.gz *pdf
