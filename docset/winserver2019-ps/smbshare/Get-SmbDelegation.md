---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: SmbScriptModule-help.xml
Module Name: SmbShare
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/smbshare/get-smbdelegation?view=windowsserver2019-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-SmbDelegation
---

# Get-SmbDelegation

## SYNOPSIS
Gets the constrained delegation authorizations for an SMB client.

## SYNTAX

```
Get-SmbDelegation [-SmbServer] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Get-SmbDelegation** cmdlet gets the constrained delegation authorizations that are currently defined for a server message block (SMB) client that you specify.
Delegation allows a user who remotes into an SMB client to perform operations on a remote SMB server.

## EXAMPLES

### Example 1: Get the constrained delegation authorizations for an SMB client
```
PS C:\> Get-SmbDelegation -SmbServer "HVSVR01"
```

This command gets the currently defined constrained delegation authorizations for the HVSRV01 server.

## PARAMETERS

### -SmbServer
Specifies the name of an SMB server.
The cmdlet gets the constrained delegation authorizations for the SMB server you specify.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES
* This cmdlet relies on Active Directory  Windows PowerShell cmdlets to perform its actions. Before you use this cmdlet, you must install the Active Directory cmdlets. To install the Active Directory cmdlets, run the following command: 
`Install-WindowsFeature RSAT-AD-PowerShell`
For more information, type `Get-Help Install-WindowsFeature`.

  This cmdlet works only with resource-based delegation, and the Active Directory forest must be at the Windows Server 2012 functional level.
To check the functional level of the Active Directory forest, use the **Get-ADForest** cmdlet.

## RELATED LINKS

[Install-WindowsFeature](/powershell/module/servermanager/install-windowsfeature)

[Disable-SmbDelegation](./Disable-SmbDelegation.md)

[Enable-SmbDelegation](./Enable-SmbDelegation.md)

