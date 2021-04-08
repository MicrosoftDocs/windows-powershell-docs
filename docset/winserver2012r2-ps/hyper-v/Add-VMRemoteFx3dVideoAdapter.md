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
online version: https://docs.microsoft.com/powershell/module/hyper-v/add-vmremotefx3dvideoadapter?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-VMRemoteFx3dVideoAdapter
---

# Add-VMRemoteFx3dVideoAdapter

## SYNOPSIS
Adds a RemoteFX video adapter in a virtual machine.

## SYNTAX

### VMName (Default)
```
Add-VMRemoteFx3dVideoAdapter [-ComputerName <String[]>] [-VMName] <String[]> [-Passthru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### VMObject
```
Add-VMRemoteFx3dVideoAdapter [-Passthru] [-VM] <VirtualMachine[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-VMRemoteFx3dVideoAdapter** cmdlet adds a RemoteFX video adapter in a virtual machine.

## EXAMPLES

### Example 1
```
PS C:\>Add-VMRemoteFx3dVideoAdapter -VMName Test
```

Adds a RemoteFX video adapter to virtual machine Test.

### Example 2
```
PS C:\>Get-VM Test | Add-VMRemoteFx3dVideoAdapter
```

Adds a RemoteFX video adapter to virtual machine Test.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which the RemoteFX video adapter is to be added.
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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Passthru
Specifies that a VMRemoteFxVideoAdapter object is to be passed through to the pipeline representing the RemoteFX video adapter to be added.

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
Specifies the virtual machine on which the RemoteFX video adapter is to be added.

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
Specifies the name of virtual machine on which the RemoteFX video adapter is to be added.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

###  
None by default; **Microsoft.HyperV.PowerShell.RemoteFxVideoAdapter** if **-PassThru** is specified.

## NOTES

## RELATED LINKS

