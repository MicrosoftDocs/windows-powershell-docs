---
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
Module Name: Hyper-V
ms.date: 10/30/2017
online version: https://learn.microsoft.com/powershell/module/hyper-v/get-vmnetworkadapter?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-VMNetworkAdapter
---

# Get-VMNetworkAdapter

## SYNOPSIS
Gets the virtual network adapters of a virtual machine, snapshot, management OS, or of a virtual machine and management OS.

## SYNTAX

### VMName (Default)
```
Get-VMNetworkAdapter [-IsLegacy <Boolean>] [-ComputerName <String[]>] [-VMName] <String[]> [[-Name] <String>]
 [<CommonParameters>]
```

### VMObject
```
Get-VMNetworkAdapter [-IsLegacy <Boolean>] [[-Name] <String>] [-VM] <VirtualMachine[]> [<CommonParameters>]
```

### ManagementOS
```
Get-VMNetworkAdapter [-ComputerName <String[]>] [[-Name] <String>] [-ManagementOS] [-SwitchName <String>]
 [<CommonParameters>]
```

### All
```
Get-VMNetworkAdapter [-ComputerName <String[]>] [[-Name] <String>] [-All] [<CommonParameters>]
```

### VMSnapshot
```
Get-VMNetworkAdapter [[-Name] <String>] [-VMSnapshot] <VMSnapshot> [<CommonParameters>]
```

## DESCRIPTION
The **Get-VMNetworkAdapter** cmdlet gets the virtual network adapters of the specified virtual machine, snapshot, or management OS.

## EXAMPLES

### Example 1
```
PS C:\>Get-VMNetworkAdapter -VMName *
```

Gets virtual network adapters from all virtual machines on the local Hyper-V host.

### Example 2
```
PS C:\>Get-VMNetworkAdapter -ManagementOS
```

Gets the virtual network adapters in the ManagementOS (i.e.
the local Hyper-V host).

### Example 3
```
PS C:\>Get-VMNetworkAdapter -All
```

Gets virtual network adapters from all virtual machines as well as the management OS.

## PARAMETERS

### -All
Specifies all virtual network adapters in the system, regardless of whether the virtual network adapter is in the management OS or in a virtual machine.

```yaml
Type: SwitchParameter
Parameter Sets: All
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies one or more Hyper-V hosts on the virtual network adapters are to be retrieved.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: VMName, ManagementOS, All
Aliases: 

Required: False
Position: Named
Default value: .
Accept pipeline input: False
Accept wildcard characters: False
```

### -IsLegacy
Specify as **$TRUE** to retrieve only legacy network adapters, or as **$FALSE** to retrieve only synthetic network adapters.
If not specified, virtual network adapters of both types are retrieved.

```yaml
Type: Boolean
Parameter Sets: VMName, VMObject
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ManagementOS
Specifies the management OS, i.e.
the virtual machine host OS.

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
Specifies the name of the network adapter to be retrieved.

```yaml
Type: String
Parameter Sets: (All)
Aliases: VMNetworkAdapterName

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SwitchName
Specifies the name of the virtual switch whose network adapters are to be retrieved.
(This parameter is available only for virtual network adapters in the management OS.)

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
Specifies the virtual machine whose virtual network adapters are to be retrieved.
The asterisk, "*", is the wildcard.
If it is specified the cmdlet returns virtual network adapters from every virtual machine in the system.

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
Specifies the name of the virtual machine whose network adapters are to be retrieved.

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

### -VMSnapshot
Specifies the snapshot whose network adapters are to be retrieved.

```yaml
Type: VMSnapshot
Parameter Sets: VMSnapshot
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

###  
**Microsoft.HyperV.PowerShell.VMInternalNetworkAdapter** if **ManagementOS** is specified; **Microsoft.HyperV.PowerShell.VMInternalNetworkAdapter** and **Microsoft.HyperV.PowerShell.VMNetworkAdapter** if **All** is specified;**Microsoft.HyperV.PowerShell.VMNetworkAdapter** in all other cases.

## NOTES

## RELATED LINKS

