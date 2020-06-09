LATEX=xelatex
LATEXOPT=-shell-escape -8bit -synctex=1 -interaction=nonstopmode
LATEXDEBUG=-file-line-error -halt-on-error

LATEXMK=latexmk
LATEXMKOPT=-pdf -pvc -use-make -view=none
LATEXMKCLEAN=-C

.PHONY: all clean

all: %.pdf : %.tex
	$(LATEXMK) $(LATEXMKOPT) -pdflatex="$(LATEX) $(LATEXOPT)" $<

debug: %.pdf %.tex
	$(LATEX) $(LATEXOPT) $(LATEXDEBUG) $<

clean:
	$(LATEXMK) $(LATEXMKCLEAN)
	-rm -rf _minted-*/ *.listing *.thm
