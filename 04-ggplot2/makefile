all: notes

notes: 
	R CMD Sweave ggplot2-notes.Rnw
	pdflatex ggplot2-notes
	pdflatex ggplot2-notes
	rm *.tex
	rm ggplot2-notes-0*.pdf
	rm -rf *.log *.bbl *.blg *.out *.toc *.aux *.fdb_latexmk *.fls
