LATEX=xelatex
LATEXOPT=-shell-escape -8bit -synctex=1 -interaction=nonstopmode
LATEXDEBUG=-file-line-error -halt-on-error
BIBTEX=biber

LATEXMK=latexmk
LATEXMKOPT=-pdf -pvc -use-make -view=none -bibtex
LATEXMKCLEAN=-c

RMFILES=.auctex-auto/ _minted-*/ *.listing *.synctex.gz *.thm *.bbl *.run.xml

.PHONY: all one debug clean

all: %.pdf : %.tex
	$(LATEXMK) $(LATEXMKOPT) -pdflatex="$(LATEX) $(LATEXOPT)" $<

one:
	$(LATEXMK) $(LATEXMKOPT) -pdflatex="$(LATEX) $(LATEXOPT)" $(ARG)

debug:
	$(LATEX) $(LATEXOPT) $(LATEXDEBUG) $(ARG)
	$(BIBTEX) $(ARG)
	$(LATEX) $(LATEXOPT) $(LATEXDEBUG) $(ARG)
	$(LATEX) $(LATEXOPT) $(LATEXDEBUG) $(ARG)

clean:
	$(LATEXMK) -c $(ARG)
	-rm -rf $(RMFILES)
