<!--- @file
  1 Introduction

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

# 1 Introduction

## 1.1 Scope

This document discusses the mechanisms and configuration entries required to
make it easy to write portable silicon modules and to port the Framework from
platform to platform.

This specification is a "requirements" specification and lists the types of
data that need to be abstracted. The set of items requiring abstraction will
need to be converted in to various implementations-global build flags, driver
specific build flags, protocols, PPIs, data structures, and build files-that
form a true porting guide.

This document focuses on data types needed for writing driver modules and
includes detailed listings of properties. Porting to a specific platform does
not require manually setting all of these values. Some values are derivable
from other values and don't need to be set directly. Also, it might be possible
to build a more intelligent way to gather the requirements for the user without
having them fill out an exhaustive list of properties.

## 1.2 Target Audience

This document is intended to be the basis for the EDK II (EDK 2.0) activity and
is designed to get feedback about what types of data need to be abstracted.

The goal of the document will be to enable the creation of implementation
documentation that talks about build and code changes, in addition to the
creation of detailed porting guides.

## 1.3 Related Information

The following publications and sources of information may be useful to you or
are referred to by this specification:

* _Extensible Firmware Interface Specification Version 1.10_, Intel, 2001,
  http://developer.intel.com/technology/efi.

* _Unified Extensible Firmware Interface Specification Version 2.0_, Unified
  EFI, Inc, 2006, http://www.uefi.org.

* _Intel(R) Platform Innovation Framework for EFI Specifications_, Intel, 2006,
  http://www.intel.com/technology/framework.

* _EDK II Module Development Environment Package Specification_, Version 0.51,
  Intel, 2006, http://www.tianocore.org.

* _EDK II Build and Packaging Architecture Specification_, Version 0.53, Intel,
  2006, http://www.tianocore.org.

* _EDK II Module Surface Area Specification_, Version 0.51, Intel, 2006,
  http://www.tianocore.org.

* _EDK II Module Development Environment Library Specification_, Version 0.58,
  Intel, 2006, http://www.tianocore.org.

* _EDK II Platform Configuration Database Infrastructure Description_, Version
  0.54, Intel, 2006, http://www.tianocore.org.

* _EDK II C Coding Standards Specification_, Version 0.51, Intel, 2006,
  http://www.tianocore.org.
