---
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
Module Name: Hyper-V
ms.date: 10/30/2017
online version: https://learn.microsoft.com/powershell/module/hyper-v/complete-vmfailover?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Complete-VMFailover
---

# Complete-VMFailover

## SYNOPSIS
Completes a virtual machine's failover process on the Replica server.
Removes all recovery points on a failed over virtual machine.

## SYNTAX

### VMName (Default)
```
Complete-VMFailover [-ComputerName <String[]>] [-VMName] <String[]> [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### VMObject
```
Complete-VMFailover [-PassThru] [-VM] <VirtualMachine[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Complete-VMFailover** cmdlet completes a virtual machine's failover process on the Replica server.
The recovery point, on which the virtual machine is failed over, is committed and all other recovery points are removed.
Failover cannot be canceled after the recovery points are removed.

## EXAMPLES

### Example 1
```
PS C:\>Complete-VMFailover VM01
```

This command completes the failover process of a virtual machine named VM01, thereby deleting all other recovery points on the server.

### Example 2
```
PS C:\>Complete-VMFailover *
```

This command completes the failover process of all virtual machines on the local host for which the failover process has been started.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which the failover process is to be completed.
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
Specifies that an object is to be passed through to the pipeline representing the virtual machine whose failover process is to be completed.

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
Specifies the virtual machine whose failover process is to be completed.

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
Specifies the name of the virtual machine whose failover process is to be completed.

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

