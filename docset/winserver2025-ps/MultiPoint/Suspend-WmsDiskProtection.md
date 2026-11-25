---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MultiPoint.dll-Help.xml
Module Name: MultiPoint
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/multipoint/suspend-wmsdiskprotection?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Suspend-WmsDiskProtection
---

# Suspend-WmsDiskProtection

## SYNOPSIS
Suspends disk protection.

## SYNTAX

```
Suspend-WmsDiskProtection [-Server <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Suspend-WmsDiskProtection** cmdlet suspends the MultiPoint disk protection feature.

## EXAMPLES

### Example 1: Suspend disk protection
```
PS C:\> Suspend-WmsDiskProtection
```

This command suspends the disk protection feature.
The cmdlet changes the configuration of the disk protection feature and restarts the computer to apply the changes.

## PARAMETERS

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

### -Server
Specifies the fully qualified host name of the MultiPoint Server that is the target of the command.
The default is localhost.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ComputerName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### System.String

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Disable-WmsDiskProtection](./Disable-WmsDiskProtection.md)

[Enable-WmsDiskProtection](./Enable-WmsDiskProtection.md)

[Get-WmsDiskProtection](./Get-WmsDiskProtection.md)

[Resume-WmsDiskProtection](./Resume-WmsDiskProtection.md)

