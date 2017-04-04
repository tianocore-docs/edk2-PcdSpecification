<!--- @file
  2 PCD Protocol

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

# 2 PCD Protocol

#### Summary

A platform database that contains a variety of current platform settings or
directives that can be accessed by a driver or application.

#### GUID

```c
#define PCD_PROTOCOL_GUID \
  { 0x11b34006, 0xd85b, 0x4d0a, { 0xa2, 0x90, 0xd5, 0xa5, 0x71, 0x31, 0xe, 0xf7 }}
```

#### Protocol Interface Structure

```c
typedef struct {
  PCD_PROTOCOL_SET_SKU              SetSku;

  PCD_PROTOCOL_GET8                 Get8;
  PCD_PROTOCOL_GET16                Get16;
  PCD_PROTOCOL_GET32                Get32;
  PCD_PROTOCOL_GET64                Get64;
  PCD_PROTOCOL_GET_POINTER          GetPtr;
  PCD_PROTOCOL_GET_BOOLEAN          GetBool;
  PCD_PROTOCOL_GET_SIZE             GetSize;

  PCD_PROTOCOL_GET_EX_8             Get8Ex;
  PCD_PROTOCOL_GET_EX_16            Get16Ex;
  PCD_PROTOCOL_GET_EX_32            Get32Ex;
  PCD_PROTOCOL_GET_EX_64            Get64Ex;
  PCD_PROTOCOL_GET_EX_POINTER       GetPtrEx;
  PCD_PROTOCOL_GET_EX_BOOLEAN       GetBoolEx;
  PCD_PROTOCOL_GET_EX_SIZE          GetSizeEx;

  PCD_PROTOCOL_SET8                 Set8;
  PCD_PROTOCOL_SET16                Set16;
  PCD_PROTOCOL_SET32                Set32;
  PCD_PROTOCOL_SET64                Set64;
  PCD_PROTOCOL_SET_POINTER          SetPtr;
  PCD_PROTOCOL_SET_BOOLEAN          SetBool;

  PCD_PROTOCOL_SET_EX_8             Set8Ex;
  PCD_PROTOCOL_SET_EX_16            Set16Ex;
  PCD_PROTOCOL_SET_EX_32            Set32Ex;
  PCD_PROTOCOL_SET_EX_64            Set64Ex;
  PCD_PROTOCOL_SET_EX_POINTER       SetPtrEx;
  PCD_PROTOCOL_SET_EX_BOOLEAN       SetBoolEx;

  PCD_PROTOCOL_CALLBACK_ON_SET      CallBackOnSet;
  PCD_PROTOCOL_CANCEL_CALLBACK      CancelCallBackOnSet;
  PCD_PROTOCOL_GET_NEXT_TOKEN       GetNextToken;
  PCD_PROTOCOL_GET_NEXT_TOKENSPACE  GetNextTokenSpace;
} PCD_PROTOCOL;
```

#### Parameters

**_`SetSku`_**

Establish a current SKU value for the PCD service to use for subsequent data
Get/Set requests.

**_`Get8`_**

Retrieve an 8-bit value from the PCD service using the standard platform
namespace.

**_`Get16`_**

Retrieve a 16-bit value from the PCD service using the standard platform
namespace.

**_`Get32`_**

Retrieve a 32-bit value from the PCD service using the standard platform
namespace.

**_`Get64`_**

Retrieve a 64-bit value from the PCD service using the standard platform
namespace.

**_`GetPtr`_**

Retrieve a pointer to a value from the PCD service using the standard platform
namespace. Can be used to retrieve an array of bytes that represent a data
structure, ASCII string, or Unicode string

**_`GetBool`_**

Retrieve a Boolean value from the PCD service using the standard platform
namespace.

**_`GetSize`_**

Retrieve the size of a particular PCD Token value using the standard platform
namespace.

**_`Get8Ex`_**

Retrieve an 8-bit value from the PCD service using a GUIDed token namespace.

**_`Get16Ex`_**

Retrieve a 16-bit value from the PCD service using a GUIDed token namespace.

**_`Get32Ex`_**

Retrieve a 32-bit value from the PCD service using a GUIDed token namespace.

**_`Get64Ex`_**

Retrieve a 64-bit value from the PCD service using a GUIDed token namespace.

**_`GetPtrEx`_**

Retrieve a pointer to a value from the PCD service using a GUIDed token
namespace. Can be used to retrieve an array of bytes that may represent a data
structure, ASCII string, or Unicode string

**_`GetBoolEx`_**

Retrieve a Boolean value from the PCD service using a GUIDed token namespace.

**_`GetSizeEx`_**

Retrieve the size of a particular PCD Token value using a GUIDed token
namespace.

**_`Set8`_**

Set an 8-bit value in the PCD service using the standard platform namespace.

**_`Set16`_**

Set a 16-bit value in the PCD service using the standard platform namespace.

**_`Set32`_**

Set a 32-bit value in the PCD service using the standard platform namespace.

**_`Set64`_**

Set a 64-bit value in the PCD service using the standard platform namespace.

**_`SetPtr`_**

Set a pointer to a value in the PCD service using the standard platform
namespace. Can be used to set an array of bytes that may represent a data
structure, ASCII string, or Unicode string

**_`SetBool`_**

Set a Boolean value in the PCD service using the standard platform namespace.

**_`Set8Ex`_**

Set an 8-bit value in the PCD service using a GUIDed token namespace.

**_`Set16Ex`_**

Set a 16-bit value in the PCD service using a GUIDed token namespace.

**_`Set32Ex`_**

Set a 32-bit value in the PCD service using a GUIDed token namespace.

**_`Set64Ex`_**

Set a 64-bit value in the PCD service using a GUIDed token namespace.

**_`SetPtrEx`_**

Set a pointer to a value in the PCD service using a GUIDed token namespace. Can
be used to set an array of bytes that may represent a data structure, ASCII
string, or Unicode string

**_`SetBoolEx`_**

Set a Boolean value in the PCD service using a GUIDed token namespace.

**_`CallBackOnSet`_**

Establish a notification to alert when a particular PCD Token value is set.

**_`CancelCallBackOnSet`_**

Cancel a previously set notification for a particular PCD Token value.

**_`GetNextToken`_**

Retrieve the next token number that is contained in the PCD name-space.

**_`GetNextTokenSpace`_**

Retrieves the next valid PCD token namespace for a given namespace.

#### Description

Callers to this protocol must be <= TPL_CALLBACK task priority level. This is
the base PCD service API that provides an abstraction for accessing
configuration content in the platform. It is a seamless mechanism for
extracting information regardless of where the information is stored (such as
in VPD, an EFI Variable, or a PCD FFS file,).

This protocol allows access to data through size-granular APIs and provides a
mechanism for a firmware component to monitor specific settings and be alerted
when a setting is changed.
