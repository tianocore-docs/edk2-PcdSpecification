<!--- @file
  PCD_PPI.CallbackOnSet()

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

## PCD_PPI.CallbackOnSet()

#### Summary

Specifies a function to be called anytime the value of a designated token is
changed.

#### Prototype

```c
typedef
EFI_STATUS
(EFIAPI *PCD_PPI_CALL_BACK_ON_SET) (
  IN CONST EFI_GUID    *Guid, OPTIONAL
  IN UINTN             CallBackToken,
  IN PCD_PPI_CALLBACK  CallBackFunction
  );
```

#### Parameters

**_`Guid`_**

The 128-bit unique value that designates which namespace to monitor. If `NULL`,
use the standard platform namespace.

**_`CallBackToken`_**

The PCD token number to monitor.

**_`CallBackFunction`_**

The function prototype that will be called when the value associated with the
**_`CallBackToken`_** is set.

#### Related Definitions

```c
typedef
VOID
(EFIAPI *PCD_PPI_CALLBACK) (
  IN EFI_GUID  *Guid, OPTIONAL,
  IN UINT      CallBackToken,
  IN VOID      *TokenData,
  IN UINTN     TokenDatSize
  );
```

#### Description

Specifies a function to be called anytime the value of a designated token is
changed.

#### Status Codes Returned

| Status Code     | Description                                                                                        |
| --------------- | -------------------------------------------------------------------------------------------------- |
| `EFI_SUCCESS`   | The PCD service has successfully established a call event for the **_`CallBackToken`_** requested. |
| `EFI_NOT_FOUND` | The PCD service could not find the referenced token number.                                        |
