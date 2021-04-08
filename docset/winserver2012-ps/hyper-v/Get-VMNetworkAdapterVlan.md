---
author: Kateyanne
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/hyper-v/get-vmnetworkadaptervlan?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-VMNetworkAdapterVlan

## SYNOPSIS
Gets the virtual LAN settings configured on a virtual network adapter.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-VMNetworkAdapterVlan [[-VMName] <String[]>] [-ComputerName <String[]>] [-VMNetworkAdapterName <String>]
```

### UNNAMED_PARAMETER_SET_2
```
Get-VMNetworkAdapterVlan [-ComputerName <String[]>] [-VMNetworkAdapterName <String>] [-ManagementOS]
```

### UNNAMED_PARAMETER_SET_3
```
Get-VMNetworkAdapterVlan [-VM] <VirtualMachine[]> [-VMNetworkAdapterName <String>]
```

### UNNAMED_PARAMETER_SET_4
```
Get-VMNetworkAdapterVlan [-VMNetworkAdapter] <VMNetworkAdapterBase[]>
```

### UNNAMED_PARAMETER_SET_5
```
Get-VMNetworkAdapterVlan [-VMSnapshot] <VMSnapshot>
```

## DESCRIPTION
The** Get-VMNetworkAdapterVlan** cmdlet gets the virtual LAN settings configured on a virtual network adapter.

## EXAMPLES

### Example 1
```
PS C:\>Get-VMNetworkAdapterVlan
```

Gets the virtual LAN settings for each virtual network adapter in all virtual machines on the system.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which the virtual LAN settings configured on a virtual network adapter are to be retrieved.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ManagementOS
Specifies that the virtual LAN settings are to be retrieved from the management (i.e.
parent, or host) operating system.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Specifies the virtual machine in which the virtual LAN settings configured on a virtual network adapter are to be retrieved.

```yaml
Type: VirtualMachine[]
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMName
Specifies the name of the virtual machine in which the virtual LAN settings configured on a virtual network adapter are to be retrieved.

Friendly name of the virtual machine

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMNetworkAdapter
Specifies the virtual network adapter for which the virtual LAN settings are to be retrieved.

```yaml
Type: VMNetworkAdapterBase[]
Parameter Sets: UNNAMED_PARAMETER_SET_4
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMNetworkAdapterName
Specifies the name of the virtual network adapter for which the virtual LAN settings are to be retrieved.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_3
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMSnapshot
Specifies the snapshot in which the virtual LAN settings are to be retrieved.

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

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS



