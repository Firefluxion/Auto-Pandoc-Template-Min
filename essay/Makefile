  
BUILDDIR=output
FILENAME=essay.md

github-action: pdf html

pdf:
	mkdir $(BUILDDIR) -p
	pandoc $(FILENAME) \
	-F pandoc-crossref \
	--citeproc \
	--from=markdown+tex_math_single_backslash+tex_math_dollars+raw_tex \
	--to=latex \
	--output=$(BUILDDIR)/$(FILENAME).pdf \
	--pdf-engine=xelatex \
	--toc \
	-N \
	--toc-depth=2 \
	-V papersize=a4paper \
	-V geometry:margin=2.5cm \
	-V lang=en-US \
	--include-in-header="layout/disable_float.tex" \
	--include-in-header="layout/mainfont_arial.tex" \
	--resource-path=figures

html:
	mkdir $(BUILDDIR) -p
	pandoc $(FILENAME) \
	--citeproc \
	--from=markdown+tex_math_single_backslash+tex_math_dollars \
	--to=html5 \
	--output=$(BUILDDIR)/$(FILENAME).html \
	--mathjax \
	--standalone \
	--resource-path=figures