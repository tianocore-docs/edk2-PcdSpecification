<!--- @file
  Summary

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

# Summary

* [EDK II Platform Configuration Database Infrastructure Description](README.md#edk-ii-platform-configuration-database-infrastructure-description)
* [1 Introduction](1_introduction/README.md#1-introduction)
  * [1.1 Scope](1_introduction/README.md#11-scope)
  * [1.2 Target Audience](1_introduction/README.md#12-target-audience)
  * [1.3 Related Information](1_introduction/README.md#13-related-information)
  * [1.4 Terms](1_introduction/14_terms.md#14-terms)
  * [1.5 Conventions Used in this Document](1_introduction/15_conventions_used_in_this_document.md#15-conventions-used-in-this-document)
    * [1.5.1 Data Structure Descriptions](1_introduction/15_conventions_used_in_this_document.md#151-data-structure-descriptions)
    * [1.5.2 Protocol Descriptions](1_introduction/15_conventions_used_in_this_document.md#152-protocol-descriptions)
    * [1.5.3 Procedure Descriptions](1_introduction/15_conventions_used_in_this_document.md#153-procedure-descriptions)
    * [1.5.4 Pseudo-Code Conventions](1_introduction/15_conventions_used_in_this_document.md#154-pseudo-code-conventions)
    * [1.5.5 Typographic Conventions](1_introduction/15_conventions_used_in_this_document.md#155-typographic-conventions)
* [2 PCD Protocol](2_pcd_protocol_definitions/README.md#2-pcd-protocol)
  * [PCD_PROTOCOL.SetSku()](2_pcd_protocol_definitions/pcdprotocol_setsku.md#pcd_protocolsetsku)
  * [PCD_PROTOCOL.Get8()](2_pcd_protocol_definitions/pcdprotocol_get8.md#pcd_protocolget8)
  * [PCD_PROTOCOL.Get16()](2_pcd_protocol_definitions/pcdprotocol_get16.md#pcd_protocolget16)
  * [PCD_PROTOCOL.Get32()](2_pcd_protocol_definitions/pcdprotocol_get32.md#pcd_protocolget32)
  * [PCD_PROTOCOL.Get64()](2_pcd_protocol_definitions/pcdprotocol_get64.md#pcd_protocolget64)
  * [PCD_PROTOCOL.GetPtr()](2_pcd_protocol_definitions/pcdprotocol_getptr.md#pcd_protocolgetptr)
  * [PCD_PROTOCOL.GetBool()](2_pcd_protocol_definitions/pcdprotocol_getbool.md#pcd_protocolgetbool)
  * [PCD_PROTOCOL.GetSize()](2_pcd_protocol_definitions/pcdprotocol_getsize.md#pcd_protocolgetsize)
  * [PCD_PROTOCOL.Get8Ex()](2_pcd_protocol_definitions/pcdprotocol_get8ex.md#pcd_protocolget8ex)
  * [PCD_PROTOCOL.Get16Ex()](2_pcd_protocol_definitions/pcdprotocol_get16ex.md#pcd_protocolget16ex)
  * [PCD_PROTOCOL.Get32Ex()](2_pcd_protocol_definitions/pcdprotocol_get32ex.md#pcd_protocolget32ex)
  * [PCD_PROTOCOL.Get64Ex()](2_pcd_protocol_definitions/pcdprotocol_get64ex.md#pcd_protocolget64ex)
  * [PCD_PROTOCOL.GetPtrEx()](2_pcd_protocol_definitions/pcdprotocol_getptrex.md#pcd_protocolgetptrex)
  * [PCD_PROTOCOL.GetBoolEx()](2_pcd_protocol_definitions/pcdprotocol_getboolex.md#pcd_protocolgetboolex)
  * [PCD_PROTOCOL.Set8()](2_pcd_protocol_definitions/pcdprotocol_set8.md#pcd_protocolset8)
  * [PCD_PROTOCOL.Set16()](2_pcd_protocol_definitions/pcdprotocol_set16.md#pcd_protocolset16)
  * [PCD_PROTOCOL.Set32()](2_pcd_protocol_definitions/pcdprotocol_set32.md#pcd_protocolset32)
  * [PCD_PROTOCOL.Set64()](2_pcd_protocol_definitions/pcdprotocol_set64.md#pcd_protocolset64)
  * [PCD_PROTOCOL.SetPtr()](2_pcd_protocol_definitions/pcdprotocol_setptr.md#pcd_protocolsetptr)
  * [PCD_PROTOCOL.SetBoolean()](2_pcd_protocol_definitions/pcdprotocol_setboolean.md#pcd_protocolsetboolean)
  * [PCD_PROTOCOL.Set8Ex()](2_pcd_protocol_definitions/pcdprotocol_set8ex.md#pcd_protocolset8ex)
  * [PCD_PROTOCOL.Set16Ex()](2_pcd_protocol_definitions/pcdprotocol_set16ex.md#pcd_protocolset16ex)
  * [PCD_PROTOCOL.Set32Ex()](2_pcd_protocol_definitions/pcdprotocol_set32ex.md#pcd_protocolset32ex)
  * [PCD_PROTOCOL.Set64Ex()](2_pcd_protocol_definitions/pcdprotocol_set64ex.md#pcd_protocolset64ex)
  * [PCD_PROTOCOL.SetPtrEx()](2_pcd_protocol_definitions/pcdprotocol_setptrex.md#pcd_protocolsetptrex)
  * [PCD_PROTOCOL.SetBoolEx()](2_pcd_protocol_definitions/pcdprotocol_setboolex.md#pcd_protocolsetboolex)
  * [PCD_PROTOCOL.CallbackOnSet()](2_pcd_protocol_definitions/pcdprotocol_callbackonset.md#pcd_protocolcallbackonset)
  * [PCD_PROTOCOL.CancelCallback()](2_pcd_protocol_definitions/pcdprotocol_cancelcallback.md#pcd_protocolcancelcallback)
  * [PCD_PROTOCOL.GetNextToken()](2_pcd_protocol_definitions/pcdprotocol_getnexttoken.md#pcd_protocolgetnexttoken)
  * [PCD_PROTOCOL.GetNextTokenSpace()](2_pcd_protocol_definitions/pcdprotocol_getnexttokenspace.md#pcd_protocolgetnexttokenspace)
* [3 PCD PPI](3_pcd_ppi_definitions/README.md#3-pcd-ppi)
  * [PCD_PPI.SetSku()](3_pcd_ppi_definitions/pcdppi_setsku.md#pcd_ppisetsku)
  * [PCD_PPI.Get8()](3_pcd_ppi_definitions/pcdppi_get8.md#pcd_ppiget8)
  * [PCD_PPI.Get16()](3_pcd_ppi_definitions/pcdppi_get16.md#pcd_ppiget16)
  * [PCD_PPI.Get32()](3_pcd_ppi_definitions/pcdppi_get32.md#pcd_ppiget32)
  * [PCD_PPI.Get64()](3_pcd_ppi_definitions/pcdppi_get64.md#pcd_ppiget64)
  * [PCD_PPI.GetPtr()](3_pcd_ppi_definitions/pcdppi_getptr.md#pcd_ppigetptr)
  * [PCD_PPI.GetBool()](3_pcd_ppi_definitions/pcdppi_getbool.md#pcd_ppigetbool)
  * [PCD_PPI.GetSize()](3_pcd_ppi_definitions/pcdppi_getsize.md#pcd_ppigetsize)
  * [PCD_PPI.Get8Ex()](3_pcd_ppi_definitions/pcdppi_get8ex.md#pcd_ppiget8ex)
  * [PCD_PPI.Get16Ex()](3_pcd_ppi_definitions/pcdppi_get16ex.md#pcd_ppiget16ex)
  * [PCD_PPI.Get32Ex()](3_pcd_ppi_definitions/pcdppi_get32ex.md#pcd_ppiget32ex)
  * [PCD_PPI.Get64Ex()](3_pcd_ppi_definitions/pcdppi_get64ex.md#pcd_ppiget64ex)
  * [PCD_PPI.GetPtrEx()](3_pcd_ppi_definitions/pcdppi_getptrex.md#pcd_ppigetptrex)
  * [PCD_PPI.GetBoolEx()](3_pcd_ppi_definitions/pcdppi_getboolex.md#pcd_ppigetboolex)
  * [PCD_PPI.Set8()](3_pcd_ppi_definitions/pcdppi_set8.md#pcd_ppiset8)
  * [PCD_PPI.Set16()](3_pcd_ppi_definitions/pcdppi_set16.md#pcd_ppiset16)
  * [PCD_PPI.Set32()](3_pcd_ppi_definitions/pcdppi_set32.md#pcd_ppiset32)
  * [PCD_PPI.Set64()](3_pcd_ppi_definitions/pcdppi_set64.md#pcd_ppiset64)
  * [PCD_PPI.SetPtr()](3_pcd_ppi_definitions/pcdppi_setptr.md#pcd_ppisetptr)
  * [PCD_PPI.SetBoolean()](3_pcd_ppi_definitions/pcdppi_setboolean.md#pcd_ppisetboolean)
  * [PCD_PPI.Set8Ex()](3_pcd_ppi_definitions/pcdppi_set8ex.md#pcd_ppiset8ex)
  * [PCD_PPI.Set16Ex()](3_pcd_ppi_definitions/pcdppi_set16ex.md#pcd_ppiset16ex)
  * [PCD_PPI.Set32Ex()](3_pcd_ppi_definitions/pcdppi_set32ex.md#pcd_ppiset32ex)
  * [PCD_PPI.Set64Ex()](3_pcd_ppi_definitions/pcdppi_set64ex.md#pcd_ppiset64ex)
  * [PCD_PPI.SetPtrEx()](3_pcd_ppi_definitions/pcdppi_setptrex.md#pcd_ppisetptrex)
  * [PCD_PPI.SetBoolEx()](3_pcd_ppi_definitions/pcdppi_setboolex.md#pcd_ppisetboolex)
  * [PCD_PPI.CallbackOnSet()](3_pcd_ppi_definitions/pcdppi_callbackonset.md#pcd_ppicallbackonset)
  * [PCD_PPI.CancelCallback()](3_pcd_ppi_definitions/pcdppi_cancelcallback.md#pcd_ppicancelcallback)
  * [PCD_PPI.GetNextToken()](3_pcd_ppi_definitions/pcdppi_getnexttoken.md#pcd_ppigetnexttoken)
  * [PCD_PPI.GetNextTokenSpace()](3_pcd_ppi_definitions/pcdppi_getnexttokenspace.md#pcd_ppigetnexttokenspace)
