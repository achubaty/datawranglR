all: multi par clean

multi: 
	R CMD Sweave multipanel-notes.Rnw
	pdflatex multipanel-notes

par:
	R CMD Sweave par-notes.Rnw
	pdflatex par-notes

clean:
	rm *.tex
	rm -rf *.log *.bbl *.blg *.out *.toc *.aux *.fdb_latexmk *.fls
