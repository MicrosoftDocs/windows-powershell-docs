---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HostCompute.PowerShell.Cmdlets.dll-Help.xml
Module Name: HostComputeService
ms.date: 12/21/2016
online version: https://learn.microsoft.com/powershell/module/hostcomputeservice/stop-computeprocess?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-ComputeProcess
---

# Stop-ComputeProcess

## SYNOPSIS
Stops a running compute system in the Hyper-V Host Compute Service.

## SYNTAX

### Id (Default)
```
Stop-ComputeProcess [-Id] <String> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Object
```
Stop-ComputeProcess -ComputeProcess <ComputeProcess[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Stop-ComputeProcess** cmdlet stops a running compute system in the Hyper-V Host Compute Service.

## EXAMPLES


## PARAMETERS

### -ComputeProcess
Specifies an array of compute systems that this cmdlet stops.
To obtain a **ComputeProcess** object, use the **Get-ComputeProcess** cmdlet.

```yaml
Type: ComputeProcess[]
Parameter Sets: Object
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### -Force
Forces the command to run without asking for user confirmation.

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

### -Id
Specifies the ID of a compute system that this cmdlet stops.

```yaml
Type: String
Parameter Sets: Id
Aliases:

Required: True
Position: 0
Default value: None
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

[Get-ComputeProcess](./Get-ComputeProcess.md)

