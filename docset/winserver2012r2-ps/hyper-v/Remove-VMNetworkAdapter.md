---
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
Module Name: Hyper-V
ms.date: 10/30/2017
online version: https://docs.microsoft.com/powershell/module/hyper-v/remove-vmnetworkadapter?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-VMNetworkAdapter
---

# Remove-VMNetworkAdapter

## SYNOPSIS
Removes one or more virtual network adapters from a virtual machine.

## SYNTAX

### VMName (Default)
```
Remove-VMNetworkAdapter [-Name <String>] [-Passthru] [-ComputerName <String[]>] [-VMName] <String[]> [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### ManagementOS
```
Remove-VMNetworkAdapter [-Name <String>] [-SwitchName <String>] [-Passthru] [-ManagementOS]
 [-ComputerName <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### VMObject
```
Remove-VMNetworkAdapter [-Name <String>] [-Passthru] [-VM] <VirtualMachine[]> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ResourceObject
```
Remove-VMNetworkAdapter [-Passthru] [-VMNetworkAdapter] <VMNetworkAdapterBase[]> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-VMNetworkAdapter** cmdlet removes one or more virtual network adapters from a virtual machine.

## EXAMPLES

### Example 1
```
PS C:\>Remove-VMNetworkAdapter -VMName Redmond -VMNetworkAdapterName Redmond_NIC1
```

This example removes network adapter Redmond_NIC1 from a virtual machine named Redmond.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which the virtual network adapter is to be removed.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: VMName, ManagementOS
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

### -ManagementOS
Specifies the management operating system  of the virtual network adapter to be removed.

```yaml
Type: SwitchParameter
Parameter Sets: ManagementOS
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the virtual network adapter to be removed.

```yaml
Type: String
Parameter Sets: VMName, ManagementOS, VMObject
Aliases: VMNetworkAdapterName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Passthru
Specifies that an object to be passed through to the pipeline representing the virtual machine network adapter to be removed.
This is a **Microsoft.HyperV.PowerShell.VMInternalNetworkAdapter** object, if **-ManagementOS** is specified; otherwise it is a **Microsoft.HyperV.PowerShell.VMNetworkAdapter** object.

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

### -SwitchName
Specifies the name of the virtual switch connected to the virtual network adapter to be removed.

```yaml
Type: String
Parameter Sets: ManagementOS
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Specifies the virtual machine that has the virtual network adapter you want to remove.

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
Specifies the name of the virtual machine that has the virtual network adapter you want to remove.

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

### -VMNetworkAdapter
Specifies the virtual machine network adapter to be removed.

```yaml
Type: VMNetworkAdapterBase[]
Parameter Sets: ResourceObject
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

###  
None by default.
If **-PassThru** is specified, **Microsoft.HyperV.PowerShell.VMInternalNetworkAdapter**, if **-ManagementOS** is also specified;otherwise **Microsoft.HyperV.PowerShell.VMNetworkAdapter**.

## NOTES

## RELATED LINKS

