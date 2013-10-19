all: notes

notes:
	Rscript -e "library(knitr); knit('ggplot2-notes.Rnw')"
	pdflatex ggplot2-notes
	pdflatex ggplot2-notes

clean:
	rm -rf *.tex *.log *.bbl *.blg *.out *.toc *.aux *.fdb_latexmk *.fls
	rm -rf cache
	rm -rf figure
