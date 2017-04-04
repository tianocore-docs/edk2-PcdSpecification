<!--- @file
  PCD_PROTOCOL.GetNextToken()

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

## PCD_PROTOCOL.GetNextToken()

#### Summary

Retrieves the next valid PCD token for a given namespace.

#### Prototype

```c
typedef
EFI_STATUS
(EFIAPI *PCD_PROTOCOL_GET_NEXT_TOKEN) (
  IN CONST EFI_GUID  *Guid, OPTIONAL
  IN OUT UINTN       *TokenNumber
  );
```

#### Parameters

**_`Guid`_**

The 128-bit unique value that designates the namespace from which to retrieve
the next token. This is an optional parameter that may be `NULL`. If this
parameter is `NULL`, then a request is being made to retrieve tokens from the
default token space.

**_`TokenNumber`_**

A pointer to the PCD token number to use to find the subsequent token number.

#### Description

Retrieves the next valid token number in a given namespace. This is useful
since the PCD infrastructure contains a sparse list of token numbers, and one
cannot a priori know what token numbers are valid in the database.

If TokenNumber is 0 and Guid is not `NULL`, then the first token from the token
space specified by Guid is returned. If TokenNumber is not 0 and Guid is not
`NULL`, then the next token in the token space specified by Guid is returned. If
TokenNumber is 0 and Guid is `NULL`, then the first token in the default token
space is returned. If TokenNumber is not 0 and Guid is `NULL`, then the next
token in the default token space is returned. The token numbers in the default
token space may not be related to token numbers in token spaces that are named
by Guid.

If the next token number can be retrieved, then it is returned in TokenNumber,
and `EFI_SUCCESS` is returned. If TokenNumber represents the last token number in
the token space specified by Guid, then `EFI_NOT_FOUND` is returned. If
TokenNumber is not present in the token space specified by Guid, then
`EFI_NOT_FOUND` is returned.

#### Status Codes Returned

| Status Code     | Description                                                          |
| --------------- | -------------------------------------------------------------------- |
| `EFI_SUCCESS`   | The PCD service retrieved the value requested.                       |
| `EFI_NOT_FOUND` | The PCD service could not find data from the requested token number. |
