---
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
Module Name: Hyper-V
ms.date: 10/30/2017
online version: https://docs.microsoft.com/powershell/module/hyper-v/disconnect-vmnetworkadapter?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Disconnect-VMNetworkAdapter
---

# Disconnect-VMNetworkAdapter

## SYNOPSIS
Disconnects a virtual network adapter from a virtual switch or Ethernet resource pool.

## SYNTAX

### Name (Default)
```
Disconnect-VMNetworkAdapter [-VMName] <String[]> [[-Name] <String[]>] [-ComputerName <String[]>] [-Passthru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Obj
```
Disconnect-VMNetworkAdapter [-VMNetworkAdapter] <VMNetworkAdapter[]> [-Passthru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Disconnect-VMNetworkAdapter** cmdlet disconnects a virtual network adapter from a virtual switch or Ethernet resource pool.

## EXAMPLES

### Example 1
```
PS C:\>Disconnect-VMNetworkAdapter -VMNetworkAdapter Test1
```

Disconnects virtual network adapter Test1.

### Example 2
```
PS C:\>Get-VMNetworkAdapter -VMName * | Where-Object {$_.SwitchName -eq 'InternetAccess'} | Disconnect-VMNetworkAdapter
```

Disconnects all virtual network adapters whose SwitchName is InternetAccess in all virtual machines on the local Hyper-V server.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which a virtual network adapter is to be disconnected.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: Name
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

### -Name
Specifies the name of the virtual network adapter to be disconnected.

```yaml
Type: String[]
Parameter Sets: Name
Aliases: VMNetworkAdapterName

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Passthru
Specifies that a **Microsoft.HyperV.PowerShell.VMNetworkAdapter** object is to be passed through to the pipeline representing the virtual network adapter to be disconnected.

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

### -VMName
Specifies the name of the virtual machine in which the virtual network adapter is to be disconnected.

```yaml
Type: String[]
Parameter Sets: Name
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMNetworkAdapter
Specifies the virtual network adapter to be disconnected.

```yaml
Type: VMNetworkAdapter[]
Parameter Sets: Obj
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

###  
None by default; **Microsoft.HyperV.PowerShell.VMNetworkAdapter** if **-PassThru** is specified.

## NOTES

## RELATED LINKS

