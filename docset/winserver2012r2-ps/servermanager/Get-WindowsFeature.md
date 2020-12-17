---
external help file: Microsoft.Windows.ServerManager.PowerShell.dll-Help.xml
Module Name: ServerManager
online version: 
schema: 2.0.0
title: Get-WindowsFeature
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 49B3C89A-8395-4638-802A-451B56019188
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-WindowsFeature

## SYNOPSIS
Gets information about Windows Server roles, role services, and features that are available for installation and installed on a specified server.

## SYNTAX

```
Get-WindowsFeature [[-Name] <String[]>] [-Vhd <String>] [-ComputerName <String>] [-Credential <PSCredential>]
 [-LogPath <String>] [<CommonParameters>]
```

## DESCRIPTION
The `Get-WindowsFeature` cmdlet gets information about features that are both available for installation and already installed on a computer that is running Windows Server 2012 R2 or an offline virtual hard disk (VHD) that is running Windows Server 2012 R2.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Get-WindowsFeature -ComputerName Server1 -Credential contoso.com\user1
```

This example gets a list of features that is available and installed on the target computer named Server1.
The credentials for user user1 in the Contoso.com domain, a user who has Administrator rights on Server1, are provided.

### EXAMPLE 2
```
PS C:\> Get-WindowsFeature -Vhd D:\ps-test\vhd1.vhd
```

This example returns a list of features that is available and installed on the specified offline VHD located at D:\ps-test\vhd1.vhd.

### EXAMPLE 3
```
PS C:\> Get-WindowsFeature -Name AD*, Web*
```

This example returns a list of available and installed features that have a command ID starting with AD or Web.

### EXAMPLE 4
```
PS C:\> Get-WindowsFeature -ComputerName Server01 | Where Installed
```

This example returns a list of features installed on a specified server, Server01.

### EXAMPLE 5
```
PS C:\> Get-WindowsFeature -ComputerName Server01 | Where InstallState -Eq Removed
```

This example returns a list of features on a specified server, Server01, that have installation files removed from the local side-by-side store, and require an external file source for installation.

## PARAMETERS

### -ComputerName
Gets the list of available rrsandf_plural from the specified remote computer that is running Windows Server 2012 R2.
The parameter accepts only one computer name.
If this parameter is not added, or no computer name is specified, the default target is the local computer.
Valid values for the parameter include a NetBIOS name, an IP address, or a fully qualified domain name of a remote computer.

To use a remote computer's IP address as the value of this parameter, your command must include the `Credential` parameter.
The computer must either be configured for HTTPS transport, or the IP address of the remote computer must be included in the WinRM TrustedHosts list on the local computer.
For information about adding a computer name to the WinRM TrustedHosts list, see "How to Add a Computer to the Trusted Host List" in about_Remote_Troubleshootinghttp://go.microsoft.com/fwlink/p/?LinkID=135188.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Cn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies a user account that has access rights to perform this action.
If the parameter is not added, or no value is specified, the default value of this parameter is the current user.
Enter a user name in one of the following formats.
Quotation marks are optional.

-- "UserName"
-- "Domain\User"
-- "User@Domain.com"
-- A Credential object returned by the Get-Credentialhttp://go.microsoft.com/fwlink/p/?LinkID=113311 cmdlet.

If a user name is entered, then a prompt for a password is displayed.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogPath
Specifies a name and path to a log file.
Add this parameter if the results of this cmdlet must be stored in a log.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the command IDs of roles, role services, or features about which to return information.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Vhd
Specifies the path to an offline VHD.
The path can either point to a VHD file, or to a location on which the VHD is already mounted by using Deployment Image Servicing and Management (DISM) tools.

The VHD can be on a local disk on the target computer, or on a network shared folder.
If the VHD is in a network shared folder, then the value of this parameter is a UNC path to the VHD.
In this case, the computer account of the computer that you are using to mount the VHD must have read and write permissions (Read/Write permissions in the File Sharing dialog box, or Full Control on the Security tab of the folder Properties dialog box) on the shared folder, or the VHD will not be accessible.
Local loopback UNC paths are not supported.
Use either of the following formats for the computer account: DOMAIN\SERVERNAME$ or SERVERNAME$.

Add the `ComputerName` parameter to specify the target computer you want to use to mount the VHD.
If the `ComputerName` parameter is not specified, then the local computer is used.
The computer that you are using to mount the VHD must be running Windows Server 2012 R2.
Any local path, such as D:\myFolder, that is specified by using this parameter is always relative to the target computer.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String[]

## OUTPUTS

### Microsoft.Windows.ServerManager.Commands.Feature[]

## NOTES

## RELATED LINKS

[Install-WindowsFeature](./Install-WindowsFeature.md)

[Uninstall-WindowsFeature](./Uninstall-WindowsFeature.md)

[Enable-ServerManagerStandardUserRemoting](./Enable-ServerManagerStandardUserRemoting.md)

[Disable-ServerManagerStandardUserRemoting](./Disable-ServerManagerStandardUserRemoting.md)

