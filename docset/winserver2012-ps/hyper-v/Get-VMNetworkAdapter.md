---
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
online version: https://learn.microsoft.com/powershell/module/hyper-v/get-vmnetworkadapter?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-VMNetworkAdapter

## SYNOPSIS
Gets the virtual network adapters of a virtual machine, snapshot, management OS, or of a virtual machine and management OS.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-VMNetworkAdapter [-VMName] <String[]> [[-Name] <String>] [-ComputerName <String[]>] [-IsLegacy <Boolean>]
```

### UNNAMED_PARAMETER_SET_2
```
Get-VMNetworkAdapter [[-Name] <String>] [-All] [-ComputerName <String[]>]
```

### UNNAMED_PARAMETER_SET_3
```
Get-VMNetworkAdapter [[-Name] <String>] [-ComputerName <String[]>] [-SwitchName <String>] [-ManagementOS]
```

### UNNAMED_PARAMETER_SET_4
```
Get-VMNetworkAdapter [-VM] <VirtualMachine[]> [[-Name] <String>] [-IsLegacy <Boolean>]
```

### UNNAMED_PARAMETER_SET_5
```
Get-VMNetworkAdapter [-VMSnapshot] <VMSnapshot> [[-Name] <String>]
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

### -ComputerName
Specifies one or more Hyper-V hosts on the virtual network adapters are to be retrieved.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_3
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
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_4
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
Parameter Sets: UNNAMED_PARAMETER_SET_3
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
Aliases: 

Required: False
Position: 2
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
Parameter Sets: UNNAMED_PARAMETER_SET_4
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMName
Specifies the name of the virtual machine whose network adapters are to be retrieved.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

### -VMSnapshot
Specifies the snapshot whose network adapters are to be retrieved.

```yaml
Type: VMSnapshot
Parameter Sets: UNNAMED_PARAMETER_SET_5
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -SwitchName
Specifies the name of the virtual switch whose network adapters are to be retrieved.
(This parameter is available only for virtual network adapters in the management OS.)

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -All
Specifies all virtual network adapters in the system, regardless of whether the virtual network adapter is in the management OS or in a virtual machine.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### 
**Microsoft.Virtualization.Powershell.VMInternalNetworkAdapter** if **ManagementOS** is specified; **Microsoft.Virtualization.Powershell.VMInternalNetworkAdapter** and **Microsoft.Virtualization.Powershell.VMNetworkAdapter** if **All** is specified;**Microsoft.Virtualization.Powershell.VMNetworkAdapter** in all other cases.

## NOTES

## RELATED LINKS



