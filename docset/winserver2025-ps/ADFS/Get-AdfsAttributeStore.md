---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/get-adfsattributestore?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-AdfsAttributeStore
---

# Get-AdfsAttributeStore

## SYNOPSIS
Gets the attribute stores of the Federation Service.

## SYNTAX

```
Get-AdfsAttributeStore [[-Name] <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AdfsAttributeStore** cmdlet gets an attribute store of the Federation Service.
If you do not specify any parameters, the cmdlet gets all attribute stores of the Federation Service.

## EXAMPLES

## PARAMETERS

### -Name
Specifies an array of names of attribute stores that this cmdlet gets.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

A string object is received by the *Name* parameter.

## OUTPUTS

### Microsoft.IdentityServer.Management.Resources.AttributeStore

Returns one or more AttributeStore objects that represent the attribute stores of the Federation Service.

## NOTES

## RELATED LINKS

[Add-AdfsAttributeStore](./Add-AdfsAttributeStore.md)

[Remove-AdfsAttributeStore](./Remove-AdfsAttributeStore.md)

[Set-AdfsAttributeStore](./Set-AdfsAttributeStore.md)

