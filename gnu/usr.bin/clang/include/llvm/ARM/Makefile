# $OpenBSD: Makefile,v 1.1 2016/09/17 16:43:51 kettenis Exp $

.include <bsd.own.mk>

LLVM_SRCS=	${.CURDIR}/../../../../../llvm

HDRS=	ARMGenAsmMatcher.inc ARMGenAsmWriter.inc \
	ARMGenCallingConv.inc ARMGenDAGISel.inc ARMGenDisassemblerTables.inc \
	ARMGenFastISel.inc ARMGenInstrInfo.inc ARMGenRegisterInfo.inc \
	ARMGenSubtargetInfo.inc \
	ARMGenMCCodeEmitter.inc ARMGenMCPseudoLowering.inc \
	ARMGenDisassemblerTables.inc

all: ${HDRS}

install:
	# Nothing here so far ...

depend:
	# Nothing here so far ...

clean cleandir:
	rm -f ${HDRS}

ARMGenRegisterInfo.inc: ${LLVM_SRCS}/lib/Target/ARM/ARM.td
	${.OBJDIR}/../../../llvm-tblgen/llvm-tblgen -gen-register-info \
		-I${LLVM_SRCS}/include -I${LLVM_SRCS}/lib/Target/ARM \
		-o ${.TARGET} ${.ALLSRC}

ARMGenDisassemblerTables.inc: ${LLVM_SRCS}/lib/Target/ARM/ARM.td
	${.OBJDIR}/../../../llvm-tblgen/llvm-tblgen -gen-disassembler \
		-I${LLVM_SRCS}/include -I${LLVM_SRCS}/lib/Target/ARM \
		-o ${.TARGET} ${.ALLSRC}

ARMGenInstrInfo.inc: ${LLVM_SRCS}/lib/Target/ARM/ARM.td
	${.OBJDIR}/../../../llvm-tblgen/llvm-tblgen -gen-instr-info \
		-I${LLVM_SRCS}/include -I${LLVM_SRCS}/lib/Target/ARM \
		-o ${.TARGET} ${.ALLSRC}

ARMGenAsmWriter.inc: ${LLVM_SRCS}/lib/Target/ARM/ARM.td
	${.OBJDIR}/../../../llvm-tblgen/llvm-tblgen -gen-asm-writer \
		-I${LLVM_SRCS}/include -I${LLVM_SRCS}/lib/Target/ARM \
		-o ${.TARGET} ${.ALLSRC}

ARMGenAsmMatcher.inc: ${LLVM_SRCS}/lib/Target/ARM/ARM.td
	${.OBJDIR}/../../../llvm-tblgen/llvm-tblgen -gen-asm-matcher \
		-I${LLVM_SRCS}/include -I${LLVM_SRCS}/lib/Target/ARM \
		-o ${.TARGET} ${.ALLSRC}

ARMGenDAGISel.inc: ${LLVM_SRCS}/lib/Target/ARM/ARM.td
	${.OBJDIR}/../../../llvm-tblgen/llvm-tblgen -gen-dag-isel \
		-I${LLVM_SRCS}/include -I${LLVM_SRCS}/lib/Target/ARM \
		-o ${.TARGET} ${.ALLSRC}

ARMGenFastISel.inc: ${LLVM_SRCS}/lib/Target/ARM/ARM.td
	${.OBJDIR}/../../../llvm-tblgen/llvm-tblgen -gen-fast-isel \
		-I${LLVM_SRCS}/include -I${LLVM_SRCS}/lib/Target/ARM \
		-o ${.TARGET} ${.ALLSRC}

ARMGenCallingConv.inc: ${LLVM_SRCS}/lib/Target/ARM/ARM.td
	${.OBJDIR}/../../../llvm-tblgen/llvm-tblgen -gen-callingconv \
		-I${LLVM_SRCS}/include -I${LLVM_SRCS}/lib/Target/ARM \
		-o ${.TARGET} ${.ALLSRC}

ARMGenSubtargetInfo.inc: ${LLVM_SRCS}/lib/Target/ARM/ARM.td
	${.OBJDIR}/../../../llvm-tblgen/llvm-tblgen -gen-subtarget \
		-I${LLVM_SRCS}/include -I${LLVM_SRCS}/lib/Target/ARM \
		-o ${.TARGET} ${.ALLSRC}

ARMGenMCCodeEmitter.inc: ${LLVM_SRCS}/lib/Target/ARM/ARM.td
	${.OBJDIR}/../../../llvm-tblgen/llvm-tblgen -gen-emitter \
		-I${LLVM_SRCS}/include -I${LLVM_SRCS}/lib/Target/ARM \
		-o ${.TARGET} ${.ALLSRC}

ARMGenMCPseudoLowering.inc: ${LLVM_SRCS}/lib/Target/ARM/ARM.td
	${.OBJDIR}/../../../llvm-tblgen/llvm-tblgen -gen-pseudo-lowering \
		-I${LLVM_SRCS}/include -I${LLVM_SRCS}/lib/Target/ARM \
		-o ${.TARGET} ${.ALLSRC}

ARMGenDisassemblerTables.inc: ${LLVM_SRCS}/lib/Target/ARM/ARM.td
	${.OBJDIR}/../../../llvm-tblgen/llvm-tblgen -gen-disassembler \
		-I${LLVM_SRCS}/include -I${LLVM_SRCS}/lib/Target/ARM \
		-o ${.TARGET} ${.ALLSRC}

.include <bsd.obj.mk>
