all: notes

notes: 
	R CMD Sweave multipanel-notes.Rnw
	pdflatex multipanel-notes
	rm *.tex
	rm -rf *.log *.bbl *.blg *.out *.toc *.aux *.fdb_latexmk *.fls
