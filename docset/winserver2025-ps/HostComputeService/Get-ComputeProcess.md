---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HostCompute.PowerShell.Cmdlets.dll-Help.xml
Module Name: HostComputeService
ms.date: 12/21/2016
online version: https://learn.microsoft.com/powershell/module/hostcomputeservice/get-computeprocess?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ComputeProcess
---

# Get-ComputeProcess

## SYNOPSIS
Gets a list of running compute systems from the Hyper-V Host Compute Service.

## SYNTAX

### Filters (Default)
```
Get-ComputeProcess [[-Name] <String[]>] [-Owner <String[]>] [-Type <ComputeProcessType[]>] [<CommonParameters>]
```

### Id
```
Get-ComputeProcess [-Id] <String[]> [<CommonParameters>]
```

## DESCRIPTION
The **Get-ComputeProcess** cmdlet gets a list of running compute systems from the Hyper-V Host Compute Service, including virtual machines and containers.

You must run this cmdlet from an elevated PowerShell session.

## EXAMPLES


## PARAMETERS

### -Id
Specifies an array of IDs of compute systems that this cmdlet gets.

```yaml
Type: String[]
Parameter Sets: Id
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the compute system that this cmdlet gets.

```yaml
Type: String[]
Parameter Sets: Filters
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Owner
Specifies the management client that owns the compute systems that this cmdlet gets.

```yaml
Type: String[]
Parameter Sets: Filters
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Type
Specifies the type of compute systems that this cmdlet gets.
The acceptable values for this parameter are: VirtualMachine and Container.

```yaml
Type: ComputeProcessType[]
Parameter Sets: Filters
Aliases:
Accepted values: Container, VirtualMachine

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Stop-ComputeProcess](./Stop-ComputeProcess.md)

