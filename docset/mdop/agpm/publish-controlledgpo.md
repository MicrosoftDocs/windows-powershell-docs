---
description: Use this topic to help manage MDOP technologies with Windows PowerShell.
external help file: Microsoft.Agpm.Client.Powershell.dll-Help.xml
ms.date: 12/05/2016
ms.devlang: powershell
schema: 2.0.0
title: Publish-ControlledGpo
---

# Publish-ControlledGpo

## SYNOPSIS
Publishes controlled GPOs.

## SYNTAX

```
Publish-ControlledGpo [[-ControlledGpos] <ControlledGpo[]>] [-Comment <String>] [-Domain <String>] [-PassThru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Publish-ControlledGpo** cmdlet publishes controlled Group Policy Objects (GPOs) that are checked in to the Advanced Group Policy Management (AGPM) archive into production.
This is the equivalent of deploying a controlled GPO to production.

## EXAMPLES

### Example 1: Publish checked in GPOs
```
PS C:\>Get-ControlledGpo -Domain "TSQA.Contoso.com" | Where {$_.VaultState -eq "CHECKED_IN" } | Publish-ControlledGpo -PassThru
Name            : TSQA Group policies
ID              : {5507363B-6AEB-4EFF-89FD-1567CD1E14E5}
CheckoutID      : 
BackupID        : {70D90CA2-E396-4549-A2C9-18EED518F6F1}
State           : CHECKED_IN
ComputerVersion : 2
UserVersion     : 2
Deployed        : 11/25/2014 9:54:11 AM
Changed         : 11/25/2014 9:54:12 AM
ChangedBy       : CONTOSO\Admin07
WmiFilterName   : 
Comment         :
```

This command uses the **Get-ControlledGpo** cmdlet to get all controlled GPOs in the specified domain.
The command passes those GPOs to the **Where-Object** cmdlet.
That cmdlet passes any GPOs that have a state of CHECKED_IN to the current cmdlet.
This cmdlet publishes all of those GPOs.
If any of the GPOs changed, the changes become live at this time.

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
Specifies an array of GPOs to publish.
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

## OUTPUTS

### Microsoft.Agpm.ControlledGpo
This cmdlet returns controlled GPO objects, if you specify the *PassThru* parameter.

## NOTES

## RELATED LINKS

[Add-ControlledGpo](./Add-ControlledGpo.md)

[Get-ControlledGpo](./Get-ControlledGpo.md)

[Lock-ControlledGpo](./Lock-ControlledGpo.md)

[Remove-ControlledGpo](./Remove-ControlledGpo.md)

[Unlock-ControlledGpo](./Unlock-ControlledGpo.md)


