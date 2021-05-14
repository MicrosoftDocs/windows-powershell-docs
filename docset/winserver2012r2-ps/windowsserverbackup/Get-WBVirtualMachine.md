---
external help file: wsbcmdlet.dll-Help.xml
Module Name: WindowsServerBackup
ms.date: 10/30/2017
online version: https://docs.microsoft.com/powershell/module/windowsserverbackup/get-wbvirtualmachine?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WBVirtualMachine
---

# Get-WBVirtualMachine

## SYNOPSIS
Gets all virtual machines and components from the backup policy.

## SYNTAX

### Default (Default)
```
Get-WBVirtualMachine [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Policy
```
Get-WBVirtualMachine [[-Policy] <WBPolicy>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Get-WBVirtualMachine** cmdlet gets all virtual machines and Hyper-V Server components from the **WBPolicy** object or the physical machine.

## EXAMPLES

### Example 1:
```
PS C:\> Get-WBVirtualMachines
```

This command queries for virtual machines and  hv_win8_2 components on the machine and lists them.

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

### -Policy
Specifies the backup policy information contained in the **WBPolicy** object to display.

```yaml
Type: WBPolicy
Parameter Sets: Policy
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Windows.ServerBackup.Commands.WBPolicy

## OUTPUTS

### Windows.ServerBackup.Commands.WBVirtualMachine[]

## NOTES

## RELATED LINKS

[Add-WBVirtualMachine](./Add-WBVirtualMachine.md)

[Remove-WBVirtualMachine](./Remove-WBVirtualMachine.md)

