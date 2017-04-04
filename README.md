<!--- @file
  README.md for EDK II Platform Configuration Database Infrastructure Description

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

<img src="media/TianocoreTitlePageLogo.jpg" width="300" />

### {{ book.title }}

{% if book.draft %}
** DRAFT FOR REVIEW **
{% else %}
** {{ book.version }} **
{% endif %}

** {{ gitbook.time|date('MM/DD/YYYY hh:mm:ss') }} **

{% if book.udkrelease %}
** {{ book.udkrelease }} **
{% endif %}


### Acknowledgements

Redistribution and use in source (original document form) and 'compiled'
forms (converted to PDF, epub, HTML and other formats) with or without
modification, are permitted provided that the following conditions are met:

1. Redistributions of source code (original document form) must retain the
   above copyright notice, this list of conditions and the following
   disclaimer as the first lines of this file unmodified.

2. Redistributions in compiled form (transformed to other DTDs, converted to
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

Copyright (c) 2009-2017, Intel Corporation. All rights reserved.


### Revision History

| Revision   | Revision History                                                                                                                      | Date       |
| ---------- | ------------------------------------------------------------------------------------------------------------------------------------- | ---------- |
| 0.10       | Initial Draft                                                                                                                         | 2/6/2006   |
| 0.20       | Added lots of PCD APIs and the definition for the PCD_IMAGE format.                                                                   | 2/19/2006  |
| 0.21       | Added VPD support and further explanations of the PCD hierarchy between module/package/platform data collection areas                 | 2/28/2006  |
| 0.22       | Corrected items in the PCD_DATA encoding to allow for a PCD token to have a GUID entry for DynamicEx access mechanism.                | 3/02/2006  |
| 0.50       | Finalized updates and removal of extraneous information. PCD Base Name definitions are covered in a separate specification.           | 3/23/2006  |
| 0.51       | Lots of minor edits throughout. Clarifications, text updated, and the .ffs format has gone through several updates.                   | 4/21/2006  |
| 0.52       | Updated the PCD SePtr routines to handle reflecting correct maximum SizeOfValue.                                                      | 6/22/2006  |
|            | Added GetNextTokenSpace routines for the PCD services                                                                                 |            |
|            | Deprecated the PCD FFS definitions - these have been relegated to implementation detail                                               |            |
| 0.53       | Removed extraneous non-PCD specific references                                                                                        | 6/30/2006  |
| 0.54       | Change EDK II.                                                                                                                        | 7/13/2006  |
| 0.55       | Drop the TPL restriction for PCD PPI since TPL is a concept in DXE phase.                                                             | 4/29/2009  |
|            | Add GetNextTokenSpace() service to the PCD PPI and PCD Protocol structures.                                                           |            |
|            | Update the PCD PPI and Protocol structures to sue the correct field names for the Get/Set services.                                   |            |
|            | Update GetNextToken() in the PPI and Protocol to clarify the meaning of a `NULL` Guid parameter that specifies the default token space. |            |
|            | Update TPL restriction for the PCD protocol to be <= TPL_CALLBACK.                                                                    |            |
| 0.56       | Convert to Gitbook                                                                                                                    | April 2017 |
