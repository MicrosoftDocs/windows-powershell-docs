---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/get-adfsaccesscontrolpolicy?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-AdfsAccessControlPolicy
---

# Get-AdfsAccessControlPolicy

## SYNOPSIS
Gets an AD FS access control policy.

## SYNTAX

```
Get-AdfsAccessControlPolicy [-Name <String[]>] [-Identifier <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AdfsAccessControlPolicy** cmdlet gets an Active Directory Federation Services (AD FS) access control policy.

## EXAMPLES

## PARAMETERS

### -Identifier
Specifies an array of IDs.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies an array of policy names.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[New-AdfsAccessControlPolicy](./New-AdfsAccessControlPolicy.md)

[Remove-AdfsAccessControlPolicy](./Remove-AdfsAccessControlPolicy.md)

[Set-AdfsAccessControlPolicy](./Set-AdfsAccessControlPolicy.md)

