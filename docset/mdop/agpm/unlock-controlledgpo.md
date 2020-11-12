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
ms.assetid: 2202E5F2-71C6-4420-AB47-E9D14A1F636B
ms.date: 12/05/2016
ms.devlang: powershell
ms.topic: reference
online version: 
schema: 2.0.0
title: Unlock-ControlledGpo
---

# Unlock-ControlledGpo

## SYNOPSIS
Unlocks controlled GPOs.

## SYNTAX

```
Unlock-ControlledGpo [[-ControlledGpos] <ControlledGpo[]>] [-Comment <String>] [-Domain <String>] [-PassThru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Unlock-ControlledGpo** cmdlet unlocks controlled Group Policy Objects (GPOs) in an Advanced Group Policy Management (AGPM) archive.
You can edit an unlocked GPO.
Unlocking a GPO is the equivalent of checking out a GPO.

## EXAMPLES

### Example 1: Unlock all locked GPOs
```
PS C:\>Get-ControlledGpo | Where {$_.VaultState -eq "CHECKED_IN"} | Unlock-ControlledGpo -Comment "Unlock all GPOs"
```

This command uses the **Get-ControlledGpo** cmdlet to get all controlled GPOs in the current domain.
The command passes those GPOs to the **Where-Object** cmdlet.
That cmdlet passes any GPOs that have a state of CHECKED_IN to the current cmdlet.
This cmdlet unlocks all of those GPOs.
The cmdlet includes an explanatory comment.

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
Specifies an array of GPOs to unlock.
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

### -PassThru
Indicates that this cmdlet returns the controlled GPOs on which the cmdlet operates.
If you do not specify this parameter, this cmdlet returns no results.

```yaml
Type: SwitchParameter
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

### Microsoft.Agpm.ControlledGpo
This cmdlet returns controlled GPO objects, if you specify the *PassThru* parameter.

## NOTES

## RELATED LINKS

[Add-ControlledGpo](./Add-ControlledGpo.md)

[Get-ControlledGpo](./Get-ControlledGpo.md)

[Lock-ControlledGpo](./Lock-ControlledGpo.md)

[Publish-ControlledGpo](./Publish-ControlledGpo.md)

[Remove-ControlledGpo](./Remove-ControlledGpo.md)


