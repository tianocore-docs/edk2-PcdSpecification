<!--- @file
  1.5 Conventions Used in this Document

  Copyright (c) 2009-2017, Intel Corporation. All rights reserved.<BR>

  Redistribution and use in source (original document form) and 'compiled'
  forms (converted to PDF, epub, HTML and other formats) with or without
  modification, are permitted provided that the following conditions are met:

  1) Redistributions of source code (original document form) must retain the
     above copyright notice, this list of conditions and the following
     disclaimer as the first lines of this file unmodified.

  2) Redistributions in compiled form (transformed to other DTDs, converted to
     PDF, epub, HTML and other formats) must reproduce the above copyright
     notice, this list of conditions and the following disclaimer in the
     documentation and/or other materials provided with the distribution.

  THIS DOCUMENTATION IS PROVIDED BY TIANOCORE PROJECT "AS IS" AND ANY EXPRESS OR
  IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF
  MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO
  EVENT SHALL TIANOCORE PROJECT  BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL,
  SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO,
  PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS;
  OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY,
  WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR
  OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS DOCUMENTATION, EVEN IF
  ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.

-->

## 1.5 Conventions Used in this Document

This document uses typographic and illustrative conventions described below.

### 1.5.1 Data Structure Descriptions

The Intel(R) Architecture processors of the IA-32 family are "little endian"
machines. This means that the low-order byte of a multi-byte data item in
memory is at the lowest address, while the high-order byte is at the highest
address. Processors of the Itanium(R) Processor Family (IPF) may be configured
for both "little endian" and "big endian" operation. All implementations
designed to conform to this specification will use "little endian" operation.

In some memory layout descriptions, certain fields are marked _reserved_.
Software must initialize such fields to zero, and ignore them when read. On an
update operation, software must preserve any reserved field.

### 1.5.2 Protocol Descriptions

The protocols described in this document generally have the following format:

#### Protocol Name

The formal name of the protocol interface.

#### Summary

A brief description of the protocol interface.

#### GUID

The 128-bit Globally Unique Identifier (GUID) for the protocol interface.

#### Protocol Interface Structure

A "C-style" data structure definition containing the procedures and data fields
produced by this protocol interface.

#### Parameters

A brief description of each field in the protocol interface structure.

#### Description

A description of the functionality provided by the interface, including any
limitations and caveats of which the caller should be aware.

#### Related Definitions

The type declarations and constants that are used in the protocol interface
structure or any of its procedures.

### 1.5.3 Procedure Descriptions

The procedures described in this document generally have the following format:

#### ProcedureName()

The formal name of the procedure.

#### Summary

A brief description of the procedure.

#### Prototype

A "C-style" procedure header defining the calling sequence.

#### Parameters

A brief description of each field in the procedure prototype.

#### Description

A description of the functionality provided by the interface, including any
limitations and caveats of which the caller should be aware.

#### Related Definitions

The type declarations and constants that are used only by this procedure.

#### Status Codes Returned

A description of any codes returned by the interface. The procedure is required
to implement any status codes listed in this table. Additional error codes may
be returned, but they will not be tested by standard compliance tests, and any
software that uses the procedure cannot depend on any of the extended error
codes that an implementation may provide.

### 1.5.4 Pseudo-Code Conventions

Pseudo-code is presented to describe algorithms in a more concise form. None of
the algorithms in this document are intended to be compiled directly. The code
is presented at a level corresponding to the surrounding text.

In describing variables, a _list_ is an unordered collection of homogeneous
objects. A _queue_ is an ordered list of homogeneous objects. Unless otherwise
noted, the ordering is assumed to be FIFO.

Pseudo-code is presented in a C-like format, using C conventions where
appropriate. The coding style, particularly the indentation style, is used for
readability and does not necessarily comply with an implementation of the _EFI
Specification_.

### 1.5.5 Typographic Conventions

The following typographic conventions are used in this document to illustrate
programming concepts:

`Code`: This typeface is use to indicate code.

**_`Argument`_**: This typeface is used to indicate arguments.

**register**:  This typeface is used to indicate a processor register.
