---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/set-adfsfarminformation?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-AdfsFarmInformation
---

# Set-AdfsFarmInformation

## SYNOPSIS
Removes a stale or offline farm node from the farm information table.

## SYNTAX

```
Set-AdfsFarmInformation [-RemoveNode <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AdfsFarmInformation** cmdlet removes a stale or offline farm node from the farm information table in order to keep the list of Active Directory Federation Services (AD FS) farm nodes current.

## EXAMPLES

### Example 1: Remove a stale node
```
PS C:\> Set-AdfsFarmInformation -RemoveNode "adfs02.contoso.com"
```

This command removes the node named adfs02.contoso.com from the farm information table.

## PARAMETERS

### -RemoveNode
Specifies an array of fully qualified domain names (FQDN) of AD FS farm nodes to remove from the farm information table.

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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AdfsFarmInformation](./Get-AdfsFarmInformation.md)

