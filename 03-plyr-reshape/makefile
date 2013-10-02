all: reshape plyr clean

plyr: 
	R CMD Sweave plyr-notes.Rnw
	pdflatex plyr-notes.tex

reshape: 
	R CMD Sweave reshape-notes.Rnw
	pdflatex reshape-notes.tex

clean:
	rm -rf *.tex *.log *.bbl *.blg *.out *.toc *.aux *.fdb_latexmk *.fls
	rm plyr-notes-00*.pdf
	rm reshape-notes-00*.pdf
