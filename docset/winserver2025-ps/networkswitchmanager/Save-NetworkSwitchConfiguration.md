---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: NetworkSwitchConfiguration.psm1-help.xml
Module Name: NetworkSwitchManager
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/networkswitchmanager/save-networkswitchconfiguration?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Save-NetworkSwitchConfiguration
---

# Save-NetworkSwitchConfiguration

## SYNOPSIS
Saves configuration for starting a network switch.

## SYNTAX

```
Save-NetworkSwitchConfiguration [-CimSession] <CimSession> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Save-NetworkSwitchConfiguration** cmdlet saves the current configuration for starting a network switch.

## EXAMPLES

### Example 1: Save the configuration for a network switch
```
PS C:\>$Session = New-CimSession -ComputerName "NetworkSwitch08"
PS C:\> Save-NetworkSwitchConfiguration -CimSession $Session
```

The first command creates a **CimSession** for a network switch, and then stores it in the **$Session** variable.
For more information about **CimSession** objects, type `Get-Help New-CimSession`.

The second command saves the configuration for NetworkSwitch08 by using the **$Session** object.

## PARAMETERS

### -CimSession
Specifies the **CimSession** that this cmdlet uses to connect to the network switch.
For more information about **CimSession** objects, type `Get-Help New-CimSession`.

```yaml
Type: CimSession
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
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

### None

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Restore-NetworkSwitchConfiguration](./Restore-NetworkSwitchConfiguration.md)

