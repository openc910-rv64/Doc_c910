Overview

C910

is  a  RISC-V  compatible  64-bit  high  performance  processor

developed by XuanTie Semiconductor Co., Ltd. It delivers industry-leading
through
performance

flow,  computing  and

in  control

frequency

architecture  and  micro-architecture  innovations.  The  C910  processor  is

based  on  the  RV64GC  instruction  set  and  implements  the  XIE  (XuanTie

Instruction Extension) technology. C910 adopts a state of the art 12 stages

out-of-order  multiple  issue  superscalar  pipeline  with  high  frequency,  IPC,

and  power  efficiency.  C910  supports  hardware  cache  coherency.  Each

cluster  contains  2  cores.  The  C910  supports  the  AXI4  bus  interface.  The

C910  uses  the  Sv39  virtual  address  system  with  XMAE  (XuanTie  Memory

Attributes  Extension)  technology.  In  addition,  C910  includes  the  standard

CLINT  and  PLIC  interrupt  controllers  and  performance  monitors.  C910

implements the XuanTie debug protocol.

Features

Feature

Architecture

SMP

Pipeline

Description

RV64GC

2 cores in each cluster

12 stages (Integer)

Floating-point Unit

Support RISC-V F, D instruction extension
Support IEEE 754-2008 standard

Bus interface

AXI4-128 master

Instruction Cache

Data Cache

64KB

64KB

www.xrvm.cn

©【杭州中天微系统有限公司】版权所有

1

Feature

L2 Cache

XuanTie extensions

Memory Management
Unit (MMU)

Description

1MB
Supporting parallel access with multi-bank

XuanTie Instruction Extension（XIE）
XuanTie Memory Attributes Extension（XMAE）

Sv39 virtual memory translation

PMP

8 regions

Interrupt Controller

Platform-Level Interrupt Controller (PLIC) for supporting wide
range of system event scenarios

XuanTie C910 Components

Processor Overview

64KB L1 caches

Sv39 virtual-memory system

RV64GC ISA supported.
Superscalar 9-12 stage
main pipeline.

I Cache

MMU

D Cache

144 sources，selectable edge
triggeror level trigger

PLIC

Interrupts

CPU Main Pipeline + FPU

PMP

Debug

Physical Memory Protection
8 regions

Core 0

Core 1

JTAG
IF

JTAG

JTAG interface for debug
interaction

AXI4.0

Master IF

CIU

L2 Cache

128-bit AXI master
interface

C910MP TOP
(openc910)

Conherence Interconnect
Unit

1MB L2 Cache

Multi-Core

◇

Support dual core homogeneous multi-core system.

◇

MOESI coherency protocol.

◇

2-way centralized snoop buffer.

◇

Exclusive memory access instructions.

◇

Integrates multi-core interrupt controllers, timers, and debuggers.

www.xrvm.cn

©【杭州中天微系统有限公司】版权所有

2

Memory sub-system

The  C910  has  64K  instruction  and  data  caches  with  cache  coherency  support.  Hardware  cache  coherency

ensures  the  consistency  of  all  caches  efficiently.  The  shared  L2  Cache  is  1MB.  Software  and  hardware

collaborative optimization of data consistency between TLB, I-Cache and D-Cache.

◇

The L1 instruction memory system has the following key features:

• VIPT, two-way set-associative instruction cache.

• Fixed cache line length of 64 bytes.

• 128-bit read interface from the L2 memory system.

◇

The L1 data memory system has the following features:

• PIPT, two-way set associative L1 data cache.

• Fixed cache line length of 64 bytes.

• 128-bit read interface from the L2 memory system.

• Up to 128-bit read data paths from the data L1 memory system to the data path.

• Up to 128-bit write data path from the data path to the L1 memory system.

◇

The L2 Cache has the following features:

• Size: 1MB.

• PIPT, 16-way set-associative structure.

• Fixed line length of 64 bytes.

• Support data prefetch.

Memory Management Unit (MMU)

◇

Sv39 virtual memory systems supported.

◇

32/17-entry fully associative I-uTLB/D-uTLB.

◇

1024-entry 4-way set-associative shared TLB.

◇

Hardware page table walker.

◇

Virtual memory support for full address space and easy hardware for fast address translation.

◇

Code/data sharing.

◇

Support for full-featured OS such as Linux.

◇

XMAE (XuanTie Memory Attributes Extension) technology extends page table entries for additional attributes.

Physical Memory Protection (PMP)

8 regions basic read/write/execute memory protection with low cost.

Performance Monitor Unit (PMU)

Program code performance tuning.

www.xrvm.cn

©【杭州中天微系统有限公司】版权所有

3

Platform-Level Interrupt Controller (PLIC)
Support multi-core interrupt control.

◇

◇

144 PLIC interrupt sources.

◇

Selectable edge trigger or level trigger.

JTAG Debug
 Support XuanTie multi-core debug.

◇

◇

◇

◇

◇

◇

 JTAG debug interface support several triggers.

Support software breakpoints.

 Check and modify CPU register resource.

Single step or multi step flexibly supported.

  High speed program download through JTAG.

Float Point Unit (FPU)
RISC-V F and D extensions.

◇

◇

Support half/single/double precision.

◇

Fully IEEE-754 compliant.

◇

Does not generate floating-point exceptions.

◇

User configurable rounding modes.

Branch Predictor
Branch Target Buffer (BTB) and Branch History Table (BHT) to speed up control codes.

◇

◇

Return Address Stack (RAS) to speed up procedure returns.

◇

Loop buffer to speed up short loops.

RV Compatibility with Custom Extensions

The  C910  is  fully  compatible  with  the  RV64GC  instruction  set  and  supports  the  standard  M/S/U  privilege

program model. The C910 includes a standard 8 region PMP and Sv39 MMU, which is fully compatible with RISC

-V Linux. The C910 includes standard CLINT and PLIC interrupt controllers and RV compatible PMU.

RV Compatibility

Component

ISA

Privilege

MMU

RV version

RV64GC

1.10

Sv39

Interrupt controller

CLINT/PLIC

Interfaces
Master AXI (M-AXI)

◇

◇

Debug (JTAG)

◇

Interrupts

◇

Low power control

www.xrvm.cn

©【杭州中天微系统有限公司】版权所有

4

Configurations

Config

Options

Core Number

L1 D-Cache Size

L1 I-Cache Size

L2-Cache Size

2

64K

64K

1M

Software Ecosystems

◇

Compiler, assembler, linker, debugger and binary tools are contributed to GNU and supported officially.

◇

Linux kernel is contributed to Linux foundation and supported officially.

◇

QEMU is contributed and supported officially.

◇

Chip Integrated Development Environment (CDS), compatible with Eclipse development.

◇

Graphical profiling and statistical analysis tools base trace data（simulator）.

◇

ICE, CK-Link Pro, high speed（1.1Mbytes/s） JTAG debug hardware.

◇

Multi-core JTAG online debug.

Linux System

C910 supports the official RISC-V Linux and its software applications ecosystem. e.g.: GNU toolchain,

Fedora, Debian, buildroot and thousands of open source software based on Linux. XuanTie will continue to

make contributions to RISC-V architecture porting in Linux ecosystem.

www.xrvm.cn

©【杭州中天微系统有限公司】版权所有

5

