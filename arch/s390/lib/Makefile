# SPDX-License-Identifier: GPL-2.0
#
# Makefile for s390-specific library files..
#

lib-y += delay.o string.o uaccess.o find.o spinlock.o
obj-y += mem.o xor.o
lib-$(CONFIG_KPROBES) += probes.o
lib-$(CONFIG_UPROBES) += probes.o

# Instrumenting memory accesses to __user data (in different address space)
# produce false positives
KASAN_SANITIZE_uaccess.o := n

obj-$(CONFIG_S390_UNWIND_SELFTEST) += test_unwind.o
CFLAGS_test_unwind.o += -fno-optimize-sibling-calls

lib-$(CONFIG_FUNCTION_ERROR_INJECTION) += error-inject.o

obj-$(CONFIG_EXPOLINE_EXTERN) += expoline/
