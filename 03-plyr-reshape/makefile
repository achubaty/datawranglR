all: notes

notes: 
	R CMD Sweave plyr-notes.Rnw
	pdflatex plyr-notes.tex
	rm plyr-notes.tex
	rm plyr-notes-concordance.tex
	rm plyr-notes-00*.pdf
	rm -rf *.log *.bbl *.blg *.out *.toc *.aux *.fdb_latexmk *.fls
