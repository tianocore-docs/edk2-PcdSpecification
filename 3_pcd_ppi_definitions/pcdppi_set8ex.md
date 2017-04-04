<!--- @file
  PCD_PPI.Set8Ex()

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

## PCD_PPI.Set8Ex()

#### Summary

Sets an 8-bit value for a given PCD token.

#### Prototype

```c
typedef
EFI_STATUS
(EFIAPI *PCD_PPI_SET_EX_8) (
  IN CONST EFI_GUID  *Guid,
  IN UINTN           TokenNumber,
  IN UINT8           Value
);
```

#### Parameters

**_`Guid`_**

The 128-bit unique value that designates the namespace from which to extract
the value.

**_`TokenNumber`_**

The PCD token number.

**_`Value`_**

The value to set for the PCD token.

#### Description

When the PCD service sets a value, it will check to ensure that the size of the
value being set is compatible with the Token's existing definition. If it is
not, an error will be returned.

#### Status Codes Returned

| Status Code             | Description                                                                                                                                                            |
| ----------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `EFI_SUCCESS`           | The PCD service has set the value requested                                                                                                                            |
| `EFI_INVALID_PARAMETER` | The PCD service determined that the size of the data being set was incompatible with a call to this function. Use `GetSize()` to retrieve the size of the target data. |
| `EFI_NOT_FOUND`         | The PCD service could not find the requested token number.                                                                                                             |
