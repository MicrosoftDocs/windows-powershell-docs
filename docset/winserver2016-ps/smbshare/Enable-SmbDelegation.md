---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: SmbScriptModule-help.xml
Module Name: SmbShare
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/smbshare/enable-smbdelegation?view=windowsserver2016-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-SmbDelegation
---

# Enable-SmbDelegation

## SYNOPSIS
Enables a constrained delegation authorization for an SMB client and server.

## SYNTAX

```
Enable-SmbDelegation [-SmbClient] <String> [-SmbServer] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Enable-SmbDelegation** cmdlet enables a constrained delegation authorization for a Server Message Block (SMB) client and server.
Delegation allows a user who remotes into an SMB client to perform operations on a remote SMB server.

## EXAMPLES

### Example 1: Enable a constrained delegation authorization for SMB clients and servers
```
PS C:\> Enable-SmbDelegation -SmbServer "FileServer01" -SmbClient "HVSVR01"
```

This command adds a new constrained delegation authorization so that a user remotely connected to the SMB client named HVSVR01 can configure resources on the SMB server named FileServer01.

## PARAMETERS

### -SmbClient
Specifies the name of the SMB client.
The cmdlet enables constrained delegation authorizations for the SMB client that you specify.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SmbServer
Specifies the name of the SMB server.
The cmdlet enables constrained delegation authorizations for the SMB server that you specify.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES
* This cmdlet relies on Active Directory Windows PowerShell cmdlets to perform its actions. Before you use this cmdlet, you must install the Active Directory cmdlets. To install the Active Directory cmdlets, run the following command: 
`Install-WindowsFeature RSAT-AD-PowerShell`
For more information, type `Get-Help Install-WindowsFeature`.

  This cmdlet works only with resource-based delegation, and the Active Directory forest must be at the Windows Server 2012 functional level.
To check the functional level of the Active Directory forest, use the Get-ADForest cmdlet.

## RELATED LINKS

[Install-WindowsFeature](/powershell/module/servermanager/install-windowsfeature)

[Disable-SmbDelegation](./Disable-SmbDelegation.md)

[Get-SmbDelegation](./Get-SmbDelegation.md)

