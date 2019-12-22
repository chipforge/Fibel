#   ************    Chipforge's Fibel   *******************************
#
#   Organisation:   Chipforge
#                   Germany / European Union
#
#   Profile:        Chipforge focus on fine System-on-Chip Cores in
#                   Verilog HDL Code which are easy understandable and
#                   adjustable. For further information see
#                           www.chipforge.org
#                   there are projects from small cores up to PCBs, too.
#
#   File:           Fibel/GNUmakefile
#
#   Purpose:        Makefile for Document Generation in LaTeX
#
#   ************    GNU Make 3.80 Source Code       ****************
#
#   ////////////////////////////////////////////////////////////////
#
#   Copyright (c)   2019, 2020 by
#                   chipforge <fibel@nospam.chipforge.org>
#
#   This source file may be used and distributed without restriction
#   provided that this copyright statement is not removed from the
#   file and that any derivative work contains the original copyright
#   notice and the associated disclaimer.
#
#   This source is free software; you can redistribute it and/or modify
#   it under the terms of the GNU General Public License as published by
#   the Free Software Foundation; either version 3 of the License, or
#   (at your option) any later version.
#
#   This source is distributed in the hope that it will be useful,
#   but WITHOUT ANY WARRANTY; without even the implied warranty of
#   MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the
#   GNU General Public License for more details.
#
#    (__)  You should have received a copy of the GNU General Public
#    oo )  License along with this program; if not, write to the
#    /_/|  Free Software Foundation Inc., 51 Franklin St., 5th Floor,
#          Boston, MA 02110-1301, USA
#
#   GNU General Public License v3.0 - http://www.gnu.org/licenses/gpl-3.0.html
#   ////////////////////////////////////////////////////////////////////

#   project specific

PROJECT =       Fibel
I18N ?=         DE

#   directory pathes

DOCUMENTSDIR =  .
OUTPUTDIR =     .

#   tool variables

MV ?=           mv
RM ?=           rm -f
TAR ?=          tar -zh
DATE :=         $(shell date +%Y%m%d)

#   project tools

LATEX ?=        pdflatex # -output-directory $(OUTPUTDIR)

#   ----------------------------------------------------------------
#               DEFAULT TARGETS
#   ----------------------------------------------------------------

#   display help screen if no target is specified

.PHONY: help
help:
	#    -------------------------------------------------------------
	#    available targets:
	#    -------------------------------------------------------------
	#
	#    help       - print this help screen
	#    clean      - clean up all intermediate files
	#    fibel [I18N=<language>] - compile language-specific fibel (default: $(I18N))
	#                              e.g. DE - deutsch, EN - english


.PHONY: clean
clean:
	$(RM) *.aux *.idx *.log *.toc *.out

#   ----------------------------------------------------------------
#               DOCUMENTATION TARGETS
#   ----------------------------------------------------------------

.PHONY: fibel
fibel:  pdf clean

#   grep all hierarchical LaTeX files and build the up-to-date PDF

.PHONY: pdf
pdf:    $(I18N)_$(PROJECT).tex
	$(LATEX) $<
	$(LATEX) $<
	$(MV) $(I18N)_$(PROJECT).pdf $(OUTPUTDIR)/$(I18N)_$(PROJECT)-$(DATE).pdf

