# SPDX-License-Identifier: GPL-2.0
# scripts/dtc makefile

hostprogs-y	:= dtc
always		:= $(hostprogs-y)

dtc-objs	:= dtc.c flattree.c fstree.c data.c livetree.c treesource.c \
		   srcpos.c checks.c util.c
dtc-objs	+= dtc-lexer.lex.c dtc-parser.tab.c

# Source files need to get at the userspace version of libfdt_env.h to compile

HOSTCFLAGS_DTC := -I$(src) -I$(src)/libfdt

HOSTCFLAGS_checks.c := $(HOSTCFLAGS_DTC)
HOSTCFLAGS_data.c := $(HOSTCFLAGS_DTC)
HOSTCFLAGS_dtc.c := $(HOSTCFLAGS_DTC)
HOSTCFLAGS_flattree.c := $(HOSTCFLAGS_DTC)
HOSTCFLAGS_fstree.c := $(HOSTCFLAGS_DTC)
HOSTCFLAGS_livetree.c := $(HOSTCFLAGS_DTC)
HOSTCFLAGS_srcpos.c := $(HOSTCFLAGS_DTC)
HOSTCFLAGS_treesource.c := $(HOSTCFLAGS_DTC)
HOSTCFLAGS_util.c := $(HOSTCFLAGS_DTC)

HOSTCFLAGS_dtc-lexer.lex.c := $(HOSTCFLAGS_DTC)
HOSTCFLAGS_dtc-parser.tab.c := $(HOSTCFLAGS_DTC)

# dependencies on generated files need to be listed explicitly
$(obj)/dtc-lexer.lex.c: $(obj)/dtc-parser.tab.h

# generated files need to be cleaned explicitly
clean-files	:= dtc-lexer.lex.c dtc-parser.tab.c dtc-parser.tab.h
