<!--- @file
  PCD_PROTOCOL.SetSku()

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

## PCD_PROTOCOL.SetSku()

#### Summary

Sets the SKU value for subsequent calls to set or get PCD token values.

#### Prototype

```c
typedef
VOID
(EFIAPI *PCD_PROTOCOL_SET_SKU) (
  IN UINTN  SkuId
  );
```

#### Parameters

**_`SkuId`_**

The SKU value to set.

#### Description

`SetSku()` sets the SKU Id to be used for subsequent calls to set or get PCD
values. `SetSku()` is normally called only once by the system.

For each item (token), the database can hold a single value that applies to all
SKUs, or multiple values, where each value is associated with a specific SKU
Id. Items with multiple, SKU-specific values are called _SKU enabled_.

The SKU Id of zero is reserved as a default. The valid **_`SkuId`_** range is 1
to 255 For tokens that are not SKU enabled, the system ignores any set SKU Id
and works with the single value for that token. For SKU-enabled tokens, the
system will use the SKU Id set by the last call to `SetSku()`. If no SKU Id is
set or the currently set SKU Id isn't valid for the specified token, the system
uses the default SKU Id. If the system attempts to use the default SKU Id and
no value has been set for that Id, the results are unpredictable.
