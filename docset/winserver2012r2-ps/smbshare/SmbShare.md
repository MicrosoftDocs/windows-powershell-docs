---
Module Name: SmbShare
Module Guid: 3AF1699D-CC54-4E54-81CF-28D2DF5CCE0A
Download Help Link: http://go.microsoft.com/fwlink/?linkid=285773
Help Version: 4.0.1.0
Locale: en-US
title: SmbShare
description: 
keywords: powershell, cmdlet
author: andreabarr
manager: jasgro
ms.date: 2017-10-29
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 6677aaa5-5508-46c0-9b81-a067ecde5d08
ms.author: v-anbarr
ms.reviewer: brianlic
---

# SmbShare Module
## Description
This reference provides cmdlet descriptions and syntax for all Server Message Block (SMB) Share-specific cmdlets. It lists the cmdlets in alphabetical order based on the verb at the beginning of the cmdlet.

## SmbShare Cmdlets
### [Block-SmbShareAccess](./Block-SmbShareAccess.md)
Adds a deny access control entry (ACE) for a trustee to the security descriptor of the Server Message Block (SMB) share.

### [Close-SmbOpenFile](./Close-SmbOpenFile.md)
Forcibly closes a file that is open by one of the clients of the Server Message Block (SMB) server.

### [Close-SmbSession](./Close-SmbSession.md)
Forcibly ends the Server Message Block (SMB) session.

### [Disable-SmbDelegation](./Disable-SmbDelegation.md)
Disables a constrained delegation authorization for an SMB client and server.

### [Enable-SmbDelegation](./Enable-SmbDelegation.md)
Enables a constrained delegation authorization for an SMB client and server.

### [Get-SmbBandwidthLimit](./Get-SmbBandwidthLimit.md)
Gets the list of SMB bandwidth caps for each traffic category.

### [Get-SmbClientConfiguration](./Get-SmbClientConfiguration.md)
Retrieves the Server Message Block (SMB) client configuration.

### [Get-SmbClientNetworkInterface](./Get-SmbClientNetworkInterface.md)
Retrieves the network interfaces used by the Server Message Block (SMB) client.

### [Get-SmbConnection](./Get-SmbConnection.md)
Retrieves the connections established from the Server Message Block (SMB) client to the SMB servers.

### [Get-SmbDelegation](./Get-SmbDelegation.md)
Gets the constrained delegation authorizations for an SMB client.

### [Get-SmbMapping](./Get-SmbMapping.md)
Retrieves the Server Message Block (SMB) client directory mappings created for a server.

### [Get-SmbMultichannelConnection](./Get-SmbMultichannelConnection.md)
Retrieves the Server Message Block (SMB) connections made between the SMB client network interfaces and the SMB server network interfaces.

### [Get-SmbMultichannelConstraint](./Get-SmbMultichannelConstraint.md)
Retrieves the constraints that define how the Server Message Block (SMB) client uses network interfaces to connect to the servers.

### [Get-SmbOpenFile](./Get-SmbOpenFile.md)
Retrieves basic information about the files that are open on behalf of the clients of the Server Message Block (SMB) server.

### [Get-SmbServerConfiguration](./Get-SmbServerConfiguration.md)
Retrieves the Server Message Block (SMB) server configuration.

### [Get-SmbServerNetworkInterface](./Get-SmbServerNetworkInterface.md)
Retrieves the network interfaces used by the Server Message Block (SMB) server.

### [Get-SmbSession](./Get-SmbSession.md)
Retrieves information about the Server Message Block (SMB) sessions that are currently established between the SMB server and the associated clients.

### [Get-SmbShare](./Get-SmbShare.md)
Retrieves the Server Message Block (SMB) shares on the computer.

### [Get-SmbShareAccess](./Get-SmbShareAccess.md)
Retrieves the access control list (ACL) of the Server Message Block (SMB) share.

### [Grant-SmbShareAccess](./Grant-SmbShareAccess.md)
Adds an allow access control entry (ACE) for a trustee to the security descriptor of the Server Message Block (SMB) share.

### [New-SmbMapping](./New-SmbMapping.md)
Creates a new Server Message Block (SMB) mapping.

### [New-SmbMultichannelConstraint](./New-SmbMultichannelConstraint.md)
Creates a new Server Message Block (SMB) multi-channel constraint for the specified server.

### [New-SmbShare](./New-SmbShare.md)
Creates a new Server Message Block (SMB) share.

### [Remove-SmbBandwidthLimit](./Remove-SmbBandwidthLimit.md)
Removes SMB bandwidth caps.

### [Remove-SmbMapping](./Remove-SmbMapping.md)
Removes the Server Message Block (SMB) mapping to an SMB share.

### [Remove-SmbMultichannelConstraint](./Remove-SmbMultichannelConstraint.md)
Removes one or more specified Server Message Block (SMB) multi-channel constraints, which determine the network interfaces to be used when connecting to specific servers.

### [Remove-SmbShare](./Remove-SmbShare.md)
Deletes the specified Server Message Block (SMB) shares.

### [Revoke-SmbShareAccess](./Revoke-SmbShareAccess.md)
Removes all of the allow access control entries (ACEs) for a trustee from the security descriptor of the Server Message Block (SMB) share.

### [Set-SmbBandwidthLimit](./Set-SmbBandwidthLimit.md)
Adds an SMB bandwidth cap.

### [Set-SmbClientConfiguration](./Set-SmbClientConfiguration.md)
Sets the Server Message Block (SMB) client configuration.

### [Set-SmbPathAcl](./Set-SmbPathAcl.md)
Sets the ACL for the file system folder to match the ACL used by an SMB share.

### [Set-SmbServerConfiguration](./Set-SmbServerConfiguration.md)
Sets the Server Message Block (SMB) server configuration.

### [Set-SmbShare](./Set-SmbShare.md)
Modifies the properties of the Server Message Block (SMB) share.

### [Unblock-SmbShareAccess](./Unblock-SmbShareAccess.md)
Removes all of the deny access control entries (ACEs) for the trustee from the security descriptor of the Server Message Block (SMB) share.

### [Update-SmbMultichannelConnection](./Update-SmbMultichannelConnection.md)
Forces the Server Message Block (SMB) client to update the multi-channel-related information.

