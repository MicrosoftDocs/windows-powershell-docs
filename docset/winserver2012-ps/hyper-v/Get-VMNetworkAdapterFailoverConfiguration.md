---
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
online version: https://docs.microsoft.com/powershell/module/hyper-v/get-vmnetworkadapterfailoverconfiguration?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-VMNetworkAdapterFailoverConfiguration

## SYNOPSIS
Gets the IP address of a virtual network adapter configured to be used when a virtual machine fails over.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-VMNetworkAdapterFailoverConfiguration [-VMName] <String[]> [-ComputerName <String[]>]
 [-VMNetworkAdapterName <String>]
```

### UNNAMED_PARAMETER_SET_2
```
Get-VMNetworkAdapterFailoverConfiguration [-VM] <VirtualMachine[]> [-VMNetworkAdapterName <String>]
```

### UNNAMED_PARAMETER_SET_3
```
Get-VMNetworkAdapterFailoverConfiguration [-VMNetworkAdapter] <VMNetworkAdapterBase[]>
```

## DESCRIPTION
The **Get-VMNetworkAdapterFailoverConfiguration** cmdlet gets the IP address configuration of a virtual network adapter configured to be used when a virtual machine fails over.

## EXAMPLES

### Example 1
```
PS C:\>Get-VMNetworkAdapterFailoverConfiguration VM01
```

This example gets the failover IP address configuration of all virtual network adapters attached to a virtual machine named VM01.

### Example 2
```
PS C:\>Get-VMNetworkAdapterFailoverConfiguration VM01 -VMNetworkAdapterName NetworkAdapter
```

This example gets the failover IP address configuration of a virtual network adapter named NetworkAdapter on a virtual machine named VM01.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which the IP address configuration of a virtual network adapter is to be retrieved.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: .
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Specifies the virtual machine for which you want to get the IP address configuration of a virtual network adapter.

```yaml
Type: VirtualMachine[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMName
Specifies the name of the virtual machine for which you want to get the IP address configuration of a virtual network adapter.

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

### -VMNetworkAdapter
Specifies the virtual network adapter whose IP address configuration you want to get.

```yaml
Type: VMNetworkAdapterBase[]
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMNetworkAdapterName
Specifies the name of the virtual network adapter whose IP address configuration you want to get.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### VMNetworkAdapterFailoverConfiguration

## NOTES

## RELATED LINKS



