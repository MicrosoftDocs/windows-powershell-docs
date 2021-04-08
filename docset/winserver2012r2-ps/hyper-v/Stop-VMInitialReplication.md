---
author: Kateyanne
description: 
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
manager: jasgro
Module Name: Hyper-V
ms.author: v-kaunu
ms.date: 10/30/2017
ms.prod: powershell
ms.reviewer: brianlic
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/hyper-v/stop-vminitialreplication?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-VMInitialReplication
---

# Stop-VMInitialReplication

## SYNOPSIS
Stops an ongoing initial replication.

## SYNTAX

### VMName (Default)
```
Stop-VMInitialReplication [-ComputerName <String[]>] [-VMName] <String[]> [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### VMReplication
```
Stop-VMInitialReplication [-VMReplication] <VMReplication[]> [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### VMObject
```
Stop-VMInitialReplication [-PassThru] [-VM] <VirtualMachine[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Stop-VMInitialReplication** cmdlet stops an ongoing initial replication that uses either a virtual machine restored from backup or the network.
It does not stop an initial replication that uses external media.
For an initial replication that uses external media, you can use this cmdlet to stop the export, which returns the virtual machine to a pending state.
After an export is finished, the initial replication cannot be stopped.

## EXAMPLES

### Example 1
```
PS C:\> Stop-VMInitialReplication VM01
```

This example stops initial replication of a virtual machine named VM01.

### Example 2
```
PS C:\>Stop-VMInitialReplication *
```

This example stops initial replication of all virtual machines whose initial replication is in progress on the local Replica server.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which an ongoing initial replication is to be stopped.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: VMName
Aliases: 

Required: False
Position: Named
Default value: .
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
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Specifies that an object is to be passed through to the pipeline representing the virtual machine whose initial replication is to be stopped.

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

### -VM
Specifies the virtual machine whose initial replication is to be stopped.

```yaml
Type: VirtualMachine[]
Parameter Sets: VMObject
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMName
Specifies the name of the virtual machine whose initial replication is to be stopped.

```yaml
Type: String[]
Parameter Sets: VMName
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMReplication
Specifies the virtual machine replication to be stopped.

```yaml
Type: VMReplication[]
Parameter Sets: VMReplication
Aliases: 

Required: True
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

## OUTPUTS

###  
None by default; **Microsoft.HyperV.PowerShell.VirtualMachine** if **-PassThru** is specified.

## NOTES

## RELATED LINKS

