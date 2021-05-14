---
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
Module Name: Hyper-V
ms.date: 10/30/2017
online version: https://docs.microsoft.com/powershell/module/hyper-v/get-vmnetworkadapterfailoverconfiguration?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-VMNetworkAdapterFailoverConfiguration
---

# Get-VMNetworkAdapterFailoverConfiguration

## SYNOPSIS
Gets the IP address of a virtual network adapter configured to be used when a virtual machine fails over.

## SYNTAX

### VMName (Default)
```
Get-VMNetworkAdapterFailoverConfiguration [-VMNetworkAdapterName <String>] [-ComputerName <String[]>]
 [-VMName] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### VMObject
```
Get-VMNetworkAdapterFailoverConfiguration [-VMNetworkAdapterName <String>] [-VM] <VirtualMachine[]> [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### ResourceObject
```
Get-VMNetworkAdapterFailoverConfiguration [-VMNetworkAdapter] <VMNetworkAdapterBase[]> [-WhatIf] [-Confirm]
 [<CommonParameters>]
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

### -VM
Specifies the virtual machine for which you want to get the IP address configuration of a virtual network adapter.

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
Specifies the name of the virtual machine for which you want to get the IP address configuration of a virtual network adapter.

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
Specifies the virtual network adapter whose IP address configuration you want to get.

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

### -VMNetworkAdapterName
Specifies the name of the virtual network adapter whose IP address configuration you want to get.

```yaml
Type: String
Parameter Sets: VMName, VMObject
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

### VMNetworkAdapterFailoverConfiguration

## NOTES

## RELATED LINKS

