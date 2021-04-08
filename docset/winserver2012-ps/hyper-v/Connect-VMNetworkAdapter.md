---
author: Kateyanne
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/hyper-v/connect-vmnetworkadapter?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Connect-VMNetworkAdapter

## SYNOPSIS
Connects a virtual network adapter to a virtual switch.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Connect-VMNetworkAdapter [-VMName] <String[]> [[-Name] <String[]>] [-SwitchName] <String>
 [-ComputerName <String[]>] [-Passthru] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Connect-VMNetworkAdapter [-VMName] <String[]> [[-Name] <String[]>] [-ComputerName <String[]>] [-Passthru]
 [-UseAutomaticConnection] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Connect-VMNetworkAdapter [-VMName] <String[]> [[-Name] <String[]>] [-VMSwitch] <VMSwitch> [-Passthru]
 [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_4
```
Connect-VMNetworkAdapter [-VMNetworkAdapter] <VMNetworkAdapter[]> [-SwitchName] <String> [-Passthru] [-Confirm]
 [-WhatIf]
```

### UNNAMED_PARAMETER_SET_5
```
Connect-VMNetworkAdapter [-VMNetworkAdapter] <VMNetworkAdapter[]> [-Passthru] [-UseAutomaticConnection]
 [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_6
```
Connect-VMNetworkAdapter [-VMNetworkAdapter] <VMNetworkAdapter[]> [-VMSwitch] <VMSwitch> [-Passthru] [-Confirm]
 [-WhatIf]
```

## DESCRIPTION
The **Connect-VMNetworkAdapter** cmdlet connects a virtual network adapter to a virtual switch.

## EXAMPLES

### Example 1
```
PS C:\>Connect-VMNetworkAdapter -VMName Test1,Test2 -Name Internet -SwitchName InternetAccess
```

Connects a virtual network adapter named Internet in virtual machines Test1 and Test2 to a virtual switch InternetAccess.

### Example 2
```
PS C:\>Get-VMNetworkAdapter -VMName Test1 | Connect-VMNetworkAdapter -SwitchName InternetAccess
```

Connects a virtual network adapter in virtual machine Test1 to virtual switch InternetAccess.

### Example 3
```
PS C:\>Get-VMSwitch InternetAccess | Connect-VMNetworkAdapter -VMName Test1
```

Connects a virtual network adapter in virtual machine Test1 to switch InternetAccess.

## PARAMETERS

### -ComputerName
Specifies one or more virtual machine hosts on which the virtual network adapter is to be connected.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: .
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the virtual network adapter to be connected.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_3
Aliases: VMNetworkAdapterName

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Passthru
Specifies that a **Microsoft.Virtualization.Powershell.VMNetworkAdapter** object is to be passed through to the pipeline representing the virtual network adapter to be connected.

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
Specifies the name of the virtual switch to which the virtual network adapter is to be connected.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_4
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseAutomaticConnection
Specifies that the network adapter is to be connected to any virtual switch in the resource pool, rather than to a specific virtual switch.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_5
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMName
Specifies the name of the virtual machine in which the network adapter is to be connected.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMNetworkAdapter
Specifies the virtual network adapter to be connected.

```yaml
Type: VMNetworkAdapter[]
Parameter Sets: UNNAMED_PARAMETER_SET_4, UNNAMED_PARAMETER_SET_5, UNNAMED_PARAMETER_SET_6
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMSwitch
Specifies the virtual switch to which the virtual network adapter is to be connected.

```yaml
Type: VMSwitch
Parameter Sets: UNNAMED_PARAMETER_SET_3, UNNAMED_PARAMETER_SET_6
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### None
Default

### Microsoft.Virtualization.Powershell.VMNetworkAdapter
If **-PassThru** is specified.

## NOTES

## RELATED LINKS



