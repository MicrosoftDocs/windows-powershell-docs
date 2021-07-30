---
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
Module Name: Hyper-V
ms.date: 10/30/2017
online version: https://docs.microsoft.com/powershell/module/hyper-v/rename-vmnetworkadapter?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Rename-VMNetworkAdapter
---

# Rename-VMNetworkAdapter

## SYNOPSIS
Renames a virtual network adapter on a virtual machine or on the management operating system.

## SYNTAX

### VMName (Default)
```
Rename-VMNetworkAdapter [-VMName] <String[]> [[-Name] <String>] [-NewName] <String> [-Passthru]
 [-ComputerName <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### VMObject
```
Rename-VMNetworkAdapter [[-Name] <String>] [-NewName] <String> [-Passthru] [-VM] <VirtualMachine[]> [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### ManagementOS
```
Rename-VMNetworkAdapter [[-Name] <String>] [-NewName] <String> [-Passthru] [-ManagementOS]
 [-ComputerName <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ResourceObject
```
Rename-VMNetworkAdapter [-NewName] <String> [-Passthru] [-VMNetworkAdapter] <VMNetworkAdapterBase[]> [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Rename-VMNetworkAdapter** cmdlet renames a virtual network adapter on a virtual machine or on the management operating system.

## EXAMPLES

### Example 1
```
PS C:\>Rename-VMNetworkAdapter -VMName Redmond -NewName CoreNet
```

This example renames all the virtual network adapters of virtual machine Redmond to CoreNet.

### Example 1
```
PS C:\>Rename-VMNetworkAdapter -VMName Kirkland -Name Private -NewName CoreNet
```

This example renames the virtual network adapter Private to CoreNet in virtual machine Kirkland.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which the virtual network adapter is to be renamed.
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
Specifies that you want to rename a virtual network adapter that belongs to the management operating system.

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
Specifies the existing name of the virtual network adapter.

```yaml
Type: String
Parameter Sets: VMName, VMObject, ManagementOS
Aliases: VMNetworkAdapterName

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NewName
Specifies the new name for the virtual network adapter.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Passthru
Specifies that an object is to be passed through to the pipeline representing the virtual network adapter to be renamed.
This is a **Microsoft.HyperV.PowerShell.VMInternalNetworkAdapter** object, if ManagementOS is specified; otherwise it is a **Microsoft.HyperV.PowerShell.VMNetworkAdapter** object.

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
Specifies the virtual machine that has the virtual network adapter you want to rename.

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
Specifies the name of the virtual machine that has the virtual network adapter you want to rename.

```yaml
Type: String[]
Parameter Sets: VMName
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMNetworkAdapter
Specifies the virtual network adapter to be renamed.

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
If **-PassThru** is specified, then a **Microsoft.HyperV.PowerShell.VMInternalNetworkAdapter** object is passed through to the pipeline if **-ManagementOS** is also specified; otherwise a **Microsoft.HyperV.PowerShell.VMNetworkAdapter** is passed.

## NOTES

## RELATED LINKS

