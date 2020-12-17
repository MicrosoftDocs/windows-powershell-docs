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
ms.assetid: 8CB93BCA-DA01-432D-BE3A-6DE8BDA26CED
ms.date: 12/05/2016
ms.devlang: powershell
ms.topic: reference
online version: 
schema: 2.0.0
title: Add-ControlledGpo
---

# Add-ControlledGpo

## SYNOPSIS
Adds GPOs to an AGPM archive.

## SYNTAX

```
Add-ControlledGpo [-PassThru] [-Comment <String>] [[-Gpos] <Gpo[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-ControlledGpo** cmdlet adds uncontrolled Group Policy Objects (GPOs) to an Advanced Group Policy Management (AGPM) archive.
That GPO becomes a controlled GPO.

## EXAMPLES

### Example 1: Add a GPO by using the pipeline operator
```
PS C:\>Get-Gpo -Name "TSQA Group policies" | Add-ControlledGpo -PassThru
Name            : TSQA Group policies
ID              : {5507363B-6AEB-4EFF-89FD-1567CD1E14E5}
CheckoutID      : 
BackupID        : {185339E4-54C1-441F-A53B-4510E93DA424}
State           : CHECKED_IN
ComputerVersion : 2
UserVersion     : 2
Deployed        : 
Changed         : 11/25/2014 9:37:18 AM
ChangedBy       : CONTOSO\Admin07
WmiFilterName   : 
Comment         :
```

This command uses the **Get-Gpo** cmdlet to get the uncontrolled GPO named TSQA Group policies.
For more information, type `Get-Help Get-Gpo`.
The command passes that GPO to the current cmdlet.
This cmdlet adds that GPO to the AGPM archive.

### Example 2: Add a GPO by using a variable
```
PS C:\>$GpoObject = Get-Gpo -Name "TSQA Group policies"
PS C:\> Add-ControlledGpo -Gpos $GpoObject -PassThru
Name            : TSQA Group policies
ID              : {5507363B-6AEB-4EFF-89FD-1567CD1E14E5}
CheckoutID      : 
BackupID        : {70D90CA2-E396-4549-A2C9-18EED518F6F1}
State           : CHECKED_IN
ComputerVersion : 2
UserVersion     : 2
Deployed        : 
Changed         : 11/25/2014 9:54:12 AM
ChangedBy       : CONTOSO\Admin07
WmiFilterName   : 
Comment         :
```

The first command uses **Get-Gpo** to get the uncontrolled GPO named TSQA Group policies, and then stores that object in the $GpoObject variable.

The second command adds the object stored in $GpoObject to the AGPM archive.

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

### -Gpos
Specifies an array of GPOs to add to the AGPM archive.
To obtain GPOs, use the **Get-Gpo** cmdlet.
For more information, type `Get-Help Get-Gpo`.

```yaml
Type: Gpo[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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

### Microsoft.GroupPolicy.Gpo
This cmdlet accepts GPO objects.

## OUTPUTS

### Microsoft.Agpm.ControlledGpo
This cmdlet returns controlled GPO objects, if you specify the *PassThru* parameter.

## NOTES

## RELATED LINKS

[Get-ControlledGpo](get-controlledgpo.md)

[Lock-ControlledGpo](lock-controlledgpo.md)

[Publish-ControlledGpo](publish-controlledgpo.md)

[Remove-ControlledGpo](remove-controlledgpo.md)

[Unlock-ControlledGpo](unlock-controlledgpo.md)


