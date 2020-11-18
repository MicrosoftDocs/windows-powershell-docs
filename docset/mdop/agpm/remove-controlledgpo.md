---
ms.technology: 
ms.mktglfcycl: manage
ms.author: v-kaunu
ms.prod: w10
ms.sitesec: library
author: Kateyanne
description: Use this topic to help manage MDOP technologies with Windows PowerShell.
external help file: Microsoft.Agpm.Client.Powershell.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro 
ms.assetid: 044E611A-C54D-4B6E-9F90-45ED6F7D202D
ms.date: 12/05/2016
ms.devlang: powershell
ms.topic: reference
online version: 
schema: 2.0.0
title: Remove-ControlledGpo
---

# Remove-ControlledGpo

## SYNOPSIS
Removes controlled GPOs from the AGPM archive.

## SYNTAX

```
Remove-ControlledGpo [[-ControlledGpos] <ControlledGpo[]>] [-Comment <String>] [-Domain <String>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-ControlledGpo** cmdlet removes controlled Group Policy Objects (GPOs) from the Advanced Group Policy Management (AGPM) archive.
A removed GPO is no longer controlled.
This cmdlet does not delete the GPO.
To remove the GPO from the production environment, use the **Remove-Gpo** cmdlet.
For more information, type `Get-Help Remove-Gpo`.

## EXAMPLES

### Example 1: Remove a GPO
```
PS C:\>Get-ControlledGpo -Domain "TSQA.Contoso.com" | Where {$_.Name -eq "test"} | Remove-ControlledGpo
```

This command uses the **Get-ControlledGpo** cmdlet to get all controlled GPOs in the specified domain.
The command passes those GPOs to the **Where-Object** cmdlet.
That cmdlet passes any GPOs named test to the current cmdlet.
This cmdlet removes that test GPO from the AGPM archive.

## PARAMETERS

### -Comment
Specifies a comment for the change that this cmdlet makes.

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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ControlledGpos
Specifies an array of GPOs to remove.
To obtain controlled GPOs, use the **Get-ControlledGpo** cmdlet.

```yaml
Type: ControlledGpo[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Domain
Specifies the fully qualified domain name (FQDN) of a domain.
This cmdlet operates on GPOs in the domain that this parameter specifies.
If the AGPM service runs as part of a different domain, and if this cmdlet specifies that domain, a trust relationship must exist between that domain and the domain of the current user or computer.

If you do not specify a domain, this cmdlet uses the domain of the current user.

If you use this cmdlet as part of a computer startup or shutdown script, and if the command does not specify this parameter, the cmdlet uses the domain of the computer.

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

### -WhatIf
Shows what would happen if the cmdlet runs. The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Agpm.ControlledGpo
This cmdlet accepts controlled GPOs.

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-ControlledGpo](./Add-ControlledGpo.md)

[Get-ControlledGpo](./Get-ControlledGpo.md)

[Lock-ControlledGpo](./Lock-ControlledGpo.md)

[Publish-ControlledGpo](./Publish-ControlledGpo.md)

[Unlock-ControlledGpo](./Unlock-ControlledGpo.md)


