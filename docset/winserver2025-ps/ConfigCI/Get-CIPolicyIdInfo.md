---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.ConfigCI.Commands.dll-Help.xml
Module Name: ConfigCI
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/configci/get-cipolicyidinfo?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-CIPolicyIdInfo
---

# Get-CIPolicyIdInfo

## SYNOPSIS
Displays Code Integrity policy information.

## SYNTAX

```
Get-CIPolicyIdInfo [-FilePath] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Get-CIPolicyIdInfo** cmdlet displays Code Integrity policy information.
Specify the .xml file of the policy to modify.

This cmdlet returns human readable content.
It is not intended for use with other cmdlets.

## EXAMPLES

### Example 1: Display Code Integrity policy information
```
PS C:\> Get-CIPolicyIdInfo -FilePath ".\Policy03.xml"

Provider  : ConfigCIPolicy
Key       : PolicyInfo
ValueName : Name
ValueType : String
Value     : CIPolicy03

Provider  : ConfigCIPolicy
Key       : PolicyInfo
ValueName : PolicyId
ValueType : String
Value     : CIP077
```

This command displays the Code Integrity policy information for the policy in the stored in the Policy03.xml file.
This policy has values for both name and ID.

## PARAMETERS

### -FilePath
Specifies the path of a Code Integrity policy .xml file.

```yaml
Type: String
Parameter Sets: (All)
Aliases: f

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

### CIPolicyIdInfo

## NOTES

## RELATED LINKS

[Set-CIPolicyIdInfo](./Set-CIPolicyIdInfo.md)

