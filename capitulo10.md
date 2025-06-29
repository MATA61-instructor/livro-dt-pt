# Chapter 10 – Assembly Language

## 10.1 Introduction

In order to build a compiler, you must have a working knowledge of at
least one kind of assembly language. And, it helps to see two or more
variations of assembly, so as to fully appreciate the distinctions between
architectures. Some of these differences, such as register structure, are
quite fundamental, while some of the differences are merely superficial.

We have observed that many students seem to think that assembly lan-
guage is rather obscure and complicated. Well, it is true that the complete
manual for a CPU is extraordinarily thick, and may document hundreds
of instructions and obscure addressing modes. However, it’s been our ex-
perience that it is really only necessary to learn a small subset of a given
assembly language (perhaps 30 instructions) in order to write a functional
compiler. Many of the additional instructions and features exist to handle
special cases for operating systems, floating point math, and multi-media
computing. You can do almost everything needed with the basic subset.

We will look at two different CPU architectures that are in wide use to-
day: X86 and ARM. The Intel X86 is a CISC architecture that has evolved
since the 1970s from 8-bit to 64-bit and is now the dominant chip in per-
sonal computers, laptops, and high performance servers. The ARM pro-
cessor is a RISC architecture began life as a 32-bit chip for the personal
computer market, and is now the dominant chip for low-power and em-
bedded devices such as mobile phones and tablets.

This chapter will give you a working knowledge of the basics of each
architecture, but you will need a good reference to look up more details.
We recommend that you consult the Intel Software Developer Manual [1]
and the ARM Architecture Reference Manual [3] for the complete details.
(Note that each section is meant to be parallel and self-contained, so some
explanatory material is repeated for both X86 and ARM.)


## 10.2
 
## 10.3 

## 10.4 



## 10.5 Further Reading

This chapter has given you a brief orientation to the core features of the
X86 and ARM architectures, enough to write simple programs in the most
direct way. However, you will certainly need to look up specific details
of individual instructions in order to better understand their options and
limitations. Now you are ready to read the detailed reference manuals and
keep them handy while you construct your compiler:

1. Intel64 and IA-32 Architectures Software Developer Manuals. Intel
Corp., 2017.http://www.intel.com/content/www/us/en/processors/
architectures-software-developer-manuals.html

2. System V Application Binary Interface, Jan Hubicka, Andreas Jaeger,
Michael Matz, and Mark Mitchell (editors), 2013. https://software.
intel.com/sites/default/files/article/402129/mpx-linux64-abi.
pdf

3. ARM Architecture Reference Manual ARMv8. ARM Limited, 2017.
https://static.docs.arm.com/ddi0487/bb/DDI0487B_b_armv8_
arm.pdf.

4. The ARM-THUMB Procedure Call Standard. ARM Limited, 2000.
http://infocenter.arm.com/help/topic/com.arm.doc.espc0002/
ATPCS.pdf.


