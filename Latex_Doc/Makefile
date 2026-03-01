# =============================================================
#  Makefile für das System Design Document (LaTeX)
#  Verwendung:
#    make          – PDF kompilieren (2 Durchläufe für Referenzen)
#    make clean    – Hilfsdateien löschen
#    make distclean– inkl. PDF löschen
# =============================================================

MAIN   = main
LATEX  = pdflatex
FLAGS  = -interaction=nonstopmode -halt-on-error

.PHONY: all clean distclean

all: $(MAIN).pdf

$(MAIN).pdf: $(MAIN).tex sections/*.tex
	$(LATEX) $(FLAGS) $(MAIN).tex
	$(LATEX) $(FLAGS) $(MAIN).tex
	@echo ""
	@echo "✓  PDF erfolgreich erstellt: $(MAIN).pdf"

clean:
	rm -f $(MAIN).aux $(MAIN).log $(MAIN).out \
	      $(MAIN).toc $(MAIN).lof $(MAIN).lol \
	      build*.log
	@echo "✓  Hilfsdateien gelöscht."

distclean: clean
	rm -f $(MAIN).pdf
	@echo "✓  PDF gelöscht."
