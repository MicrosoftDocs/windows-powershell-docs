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
ms.assetid: 2C747213-D020-4EED-BA43-CF2AA4271BBE
ms.date: 12/05/2016
ms.devlang: powershell
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-ControlledGpo
---

# Get-ControlledGpo

## SYNOPSIS
Gets controlled GPOs for a domain.

## SYNTAX

```
Get-ControlledGpo [-Domain <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-ControlledGpo** cmdlet gets the controlled Group Policy Objects (GPOs) from an Advanced Group Policy Management (AGPM) archive for a domain.
You can use this cmdlet to view state information for controlled GPOs.
Use the **Get-Gpo** cmdlet to view uncontrolled GPOs.
For more information, type `Get-Help Get-Gpo`.

## EXAMPLES

### Example 1: Get all GPOs and then filter results
```
PS C:\>Get-ControlledGpo -Domain "TQSA.Contoso.com" | Where {$_.name -eq "TSQA Group policies"}
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

This command gets all controlled GPOs from the domain TQSA.Contoso.com, and then passes them to the **Where-Object** cmdlet.
That cmdlet returns the GPO from those results named TSQA Group policies.

## PARAMETERS

### -Domain
Specifies the fully qualified domain name (FQDN) of a domain.
This cmdlet gets GPOs in the domain that this parameter specifies.
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.Agpm.ControlledGpo
This cmdlet returns controlled GPO objects.

## NOTES

## RELATED LINKS

[Add-ControlledGpo](./Add-ControlledGpo.md)

[Lock-ControlledGpo](./Lock-ControlledGpo.md)

[Publish-ControlledGpo](./Publish-ControlledGpo.md)

[Remove-ControlledGpo](./Remove-ControlledGpo.md)

[Unlock-ControlledGpo](./Unlock-ControlledGpo.md)


