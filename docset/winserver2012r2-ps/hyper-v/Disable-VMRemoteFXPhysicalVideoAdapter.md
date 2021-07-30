---
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
Module Name: Hyper-V
ms.date: 10/30/2017
online version: https://docs.microsoft.com/powershell/module/hyper-v/disable-vmremotefxphysicalvideoadapter?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-VMRemoteFXPhysicalVideoAdapter
---

# Disable-VMRemoteFXPhysicalVideoAdapter

## SYNOPSIS
Disables one or more RemoteFX physical video adapters from use with RemoteFX-enabled virtual machines.

## SYNTAX

### GPUByName (Default)
```
Disable-VMRemoteFXPhysicalVideoAdapter [-ComputerName <String[]>] [-Name] <String[]> [-Passthru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### GPUByObject
```
Disable-VMRemoteFXPhysicalVideoAdapter [-GPU] <VMRemoteFXPhysicalVideoAdapter[]> [-Passthru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Disable-VMRemoteFXPhysicalVideoAdapter** disables one or more RemoteFX physical video adapter from use with RemoteFX-enabled virtual machines.

## EXAMPLES

### Example 1
```
PS C:\>Disable-VMRemoteFXPhysicalVideoAdapter -Name *Nvidia*
```

This example disables all RemoteFX physical video adapters that include the string "Nvidia" in their names.

### Example 2
```
PS C:\>Get-VMRemoteFXPhysicalVideoAdapter -Name *Nvidia* | Disable-VMRemotePhysicalVideoAdapter
```

This example disables all RemoteFX physical video adapters that include the string "Nvidia" in their names.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which the RemoteFX physical video adapters are to be disabled.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: GPUByName
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

### -GPU
Specifies one or more RemoteFX physical video adapters to disable.

```yaml
Type: VMRemoteFXPhysicalVideoAdapter[]
Parameter Sets: GPUByObject
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies an array of names of adapters.
The cmdlet disables the RemoteFX physical video adapters that you specify.

```yaml
Type: String[]
Parameter Sets: GPUByName
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Passthru
Specifies that **Microsoft.HyperV.PowerShell.VMRemoteFXPhysicalVideoAdapter** objects are to be passed to the pipeline representing the RemoteFX physical video adapters to be disabled.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.HyperV.PowerShell.VMRemoteFXPhysicalVideoAdapter[]

### System.String[]

## OUTPUTS

###  
None by default; **Microsoft.HyperV.PowerShell.VMRemoteFXPhysicalVideoAdapter** if **-PassThru** is specified.

## NOTES

## RELATED LINKS

