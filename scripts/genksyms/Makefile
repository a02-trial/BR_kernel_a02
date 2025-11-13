# SPDX-License-Identifier: GPL-2.0

hostprogs-y	:= genksyms
always		:= $(hostprogs-y)

genksyms-objs	:= genksyms.c parse.tab.c lex.lex.c

# -I needed for generated C source (shipped source)
HOSTCFLAGS_parse.tab.c := -I$(src)
HOSTCFLAGS_lex.lex.c := -I$(src)

# dependencies on generated files need to be listed explicitly
$(obj)/lex.lex.c: $(obj)/parse.tab.h

clean-files	:= lex.lex.c parse.tab.c parse.tab.h
