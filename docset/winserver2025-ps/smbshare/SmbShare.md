---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
Download Help Link: https://aka.ms/winsvr-2025-pshelp
Help Version: 5.0.1.1
Locale: en-US
Module Guid: 3af1699d-cc54-4e54-81cf-28d2df5cce0a
Module Name: SmbShare
ms.date: 06/23/2022
title: SmbShare
---

# SmbShare Module
## Description
This reference provides cmdlet descriptions and syntax for all Server Message Block (SMB)
Share-specific cmdlets. It lists the cmdlets in alphabetical order based on the verb at the
beginning of the cmdlet.

## SmbShare Cmdlets
### [Block-SmbShareAccess](./Block-SmbShareAccess.md)
Adds a deny ACE for a trustee to the security descriptor of the SMB share.

### [Close-SmbOpenFile](./Close-SmbOpenFile.md)
Closes a file that is open by one of the clients of the SMB server.

### [Close-SmbSession](./Close-SmbSession.md)
Ends forcibly the SMB session.

### [Disable-SmbDelegation](./Disable-SmbDelegation.md)
Disables a constrained delegation authorization for an SMB client and server.

### [Enable-SmbDelegation](./Enable-SmbDelegation.md)
Enables a constrained delegation authorization for an SMB client and server.

### [Get-SmbBandwidthLimit](./Get-SmbBandwidthLimit.md)
Gets the list of SMB bandwidth caps for each traffic category.

### [Get-SmbClientConfiguration](./Get-SmbClientConfiguration.md)
Retrieves the SMB client configuration.

### [Get-SmbClientNetworkInterface](./Get-SmbClientNetworkInterface.md)
Retrieves the network interfaces used by the SMB client.

### [Get-SmbConnection](./Get-SmbConnection.md)
Retrieves the connections established from the SMB client to the SMB servers.

### [Get-SmbDelegation](./Get-SmbDelegation.md)
Gets the constrained delegation authorizations for an SMB client.

### [Get-SmbGlobalMapping](./Get-SmbGlobalMapping.md)
Retrieves the properties of an SMB global mapping.

### [Get-SmbMapping](./Get-SmbMapping.md)
Retrieves the SMB client directory mappings created for a server.

### [Get-SmbMultichannelConnection](./Get-SmbMultichannelConnection.md)
Retrieves the SMB connections made between the SMB client network interfaces and the SMB server
network interfaces.

### [Get-SmbMultichannelConstraint](./Get-SmbMultichannelConstraint.md)
Retrieves the constraints that define how the SMB client uses network interfaces to connect to the
servers.

### [Get-SmbOpenFile](./Get-SmbOpenFile.md)
Retrieves basic information about the files that are open on behalf of the clients of the SMB
server.

### [Get-SmbServerCertificateMapping](./Get-SmbServerCertificateMapping.md)
Retrieves a certificate association with the SMB server for SMB over QUIC.

### [Get-SmbServerCertProps](./Get-SmbServerCertProps.md)
Retrieves an SMB over QUIC-mapped certificate's properties and tests certificate validity.

### [Get-SmbServerConfiguration](./Get-SmbServerConfiguration.md)
Retrieves the SMB server configuration.

### [Get-SmbServerNetworkInterface](./Get-SmbServerNetworkInterface.md)
Retrieves the network interfaces used by the SMB server.

### [Get-SmbSession](./Get-SmbSession.md)
Retrieves information about the SMB sessions that are currently established between the SMB server
and the associated clients.

### [Get-SmbShare](./Get-SmbShare.md)
Retrieves the SMB shares on the computer.

### [Get-SmbShareAccess](./Get-SmbShareAccess.md)
Retrieves the ACL of the SMB share.

### [Grant-SmbShareAccess](./Grant-SmbShareAccess.md)
Adds an allow ACE for a trustee to the security descriptor of the SMB share.

### [New-SmbGlobalMapping](./New-SmbGlobalMapping.md)
Creates an SMB global mapping.

### [New-SmbMapping](./New-SmbMapping.md)
Creates an SMB mapping.

### [New-SmbMultichannelConstraint](./New-SmbMultichannelConstraint.md)
Creates an SMB multi-channel constraint for the specified server.

### [New-SmbServerCertificateMapping](./New-SmbServerCertificateMapping.md)
Creates a certificate association with the SMB server for SMB over QUIC.

### [New-SmbShare](./New-SmbShare.md)
Creates an SMB share.

### [Remove-SmbBandwidthLimit](./Remove-SmbBandwidthLimit.md)
Removes SMB bandwidth caps.

### [Remove-SmbComponent](./Remove-SmbComponent.md)
Removes SMB1 components.

### [Remove-SmbGlobalMapping](./Remove-SmbGlobalMapping.md)
Removes an SMB global mapping to an SMB share.

### [Remove-SmbMapping](./Remove-SmbMapping.md)
Removes the SMB mapping to an SMB share.

### [Remove-SmbMultichannelConstraint](./Remove-SmbMultichannelConstraint.md)
Removes SMB multi-channel constraints.

### [Remove-SmbServerCertificateMapping](./Remove-SmbServerCertificateMapping.md)
Removes a certificate mapping from the SMB server for SMB over QUIC.

### [Remove-SmbShare](./Remove-SmbShare.md)
Deletes the specified SMB shares.

### [Reset-SmbClientConfiguration](./Reset-SmbClientConfiguration.md)
Resets the Server Message Block (SMB) client configuration parameters to their default values.

### [Reset-SmbServerConfiguration](./Reset-SmbServerConfiguration.md)
Resets the Server Message Block (SMB) server configuration parameters to their default values.

### [Revoke-SmbShareAccess](./Revoke-SmbShareAccess.md)
Removes all of the allow ACEs for a trustee from the security descriptor of the SMB share.

### [Set-SmbBandwidthLimit](./Set-SmbBandwidthLimit.md)
Adds an SMB bandwidth cap.

### [Set-SmbClientConfiguration](./Set-SmbClientConfiguration.md)
Sets the SMB client configuration.

### [Set-SmbPathAcl](./Set-SmbPathAcl.md)
Sets the ACL for the file system folder to match the ACL used by an SMB share.

### [Set-SmbServerCertificateMapping](./Set-SmbServerCertificateMapping.md)
Modifies a certificate association with the SMB server for SMB over QUIC.

### [Set-SmbServerConfiguration](./Set-SmbServerConfiguration.md)
Sets the Server Message Block (SMB) server configuration.

### [Set-SmbShare](./Set-SmbShare.md)
Modifies the properties of the SMB share.

### [Unblock-SmbShareAccess](./Unblock-SmbShareAccess.md)
Removes all of the deny ACEs for the trustee from the security descriptor of the SMB share.

### [Update-SmbMultichannelConnection](./Update-SmbMultichannelConnection.md)
Forces the SMB client to update the multi-channel-related information.
