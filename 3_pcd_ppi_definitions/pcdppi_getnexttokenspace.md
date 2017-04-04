<!--- @file
  PCD_PPI.GetNextTokenSpace()

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

## PCD_PPI.GetNextTokenSpace()

#### Summary

Retrieves the next valid PCD token namespace for a given namespace.

#### Prototype

```c
typedef
EFI_STATUS
(EFIAPI *PCD_PROTOCOL_GET_NEXT_TOKEN) (
  IN OUT CONST EFI_GUID  **Guid
  );
```

#### Parameters

**_`Guid`_**

An indirect pointer to `EFI_GUID.` On input, it designates a known token
namespace from which the search will start. On output, it designates the next
valid token namespace on the platform. If **_`*Guid`_** is `NULL`, then the
GUID of the first token space of the current platform is returned. If the
search cannot locate the next valid token namespace, an error is returned and
the value of **_`*Guid`_** is undefined.

#### Description

Gets the next valid token namespace for a given namespace. This is useful for
traversing the valid token namespaces on a platform.

#### Status Codes Returned

| Status Code     | Description                                                    |
| --------------- | -------------------------------------------------------------- |
| `EFI_SUCCESS`   | The PCD service retrieved the value requested.                 |
| `EFI_NOT_FOUND` | The PCD service could not find the next valid token namespace. |
