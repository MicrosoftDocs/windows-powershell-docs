---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MultiPoint.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Resume-WmsDiskProtection
ms.reviewer:
ms.assetid: 70D33C59-689D-44C3-A174-FA8E1A0136FC
---

# Resume-WmsDiskProtection

## SYNOPSIS
Switches disk protection to discard mode.

## SYNTAX

```
Resume-WmsDiskProtection [-Server <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Resume-WmsDiskProtection** cmdlet switches the disk protection feature from passive mode to discard mode, and restarts the computer to apply the state change.

## EXAMPLES

### Example 1: Switch to discard mode
```
PS C:\> Resume-WmsDiskProtection -Server "sample.microsoft.com"
```

This command changes the disk protection feature configuration from passive to discard mode, and the computer is restarted to apply the state change.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Disable-WmsDiskProtection](./Disable-WmsDiskProtection.md)

[Enable-WmsDiskProtection](./Enable-WmsDiskProtection.md)

[Get-WmsDiskProtection](./Get-WmsDiskProtection.md)

[Suspend-WmsDiskProtection](./Suspend-WmsDiskProtection.md)

