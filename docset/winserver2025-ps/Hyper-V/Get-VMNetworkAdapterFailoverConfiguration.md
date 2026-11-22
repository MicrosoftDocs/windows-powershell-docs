---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hyper-v/get-vmnetworkadapterfailoverconfiguration?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-VMNetworkAdapterFailoverConfiguration
---

# Get-VMNetworkAdapterFailoverConfiguration

## SYNOPSIS
Gets the IP address of a virtual network adapter configured to be used when a virtual machine fails over.

## SYNTAX

### VMName (Default)
```
Get-VMNetworkAdapterFailoverConfiguration [-CimSession <CimSession[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential[]>] [-VMName] <String[]> [-VMNetworkAdapterName <String>] [<CommonParameters>]
```

### VMObject
```
Get-VMNetworkAdapterFailoverConfiguration [-VM] <VirtualMachine[]> [-VMNetworkAdapterName <String>]
 [<CommonParameters>]
```

### ResourceObject
```
Get-VMNetworkAdapterFailoverConfiguration [-VMNetworkAdapter] <VMNetworkAdapter[]> [<CommonParameters>]
```

## DESCRIPTION
The **Get-VMNetworkAdapterFailoverConfiguration** cmdlet gets the IP address configuration of a virtual network adapter configured to be used when a virtual machine fails over.

## EXAMPLES

### Example 1
```
PS C:\> Get-VMNetworkAdapterFailoverConfiguration VM01
```

This example gets the failover IP address configuration of all virtual network adapters attached to a virtual machine named VM01.

### Example 2
```
PS C:\> Get-VMNetworkAdapterFailoverConfiguration VM01 -VMNetworkAdapterName NetworkAdapter
```

This example gets the failover IP address configuration of a virtual network adapter named NetworkAdapter on a virtual machine named VM01.

## PARAMETERS

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: VMName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies one or more Hyper-V hosts on which the IP address configuration of a virtual network adapter is to be retrieved.
NetBIOS names, IP addresses, and fully qualified domain names are allowable.
The default is the local computer.
Use localhost or a dot (.) to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: VMName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies one or more user accounts that have permission to perform this action.
The default is the current user.

```yaml
Type: PSCredential[]
Parameter Sets: VMName
Aliases:

Required: False
Position: Named
Default value: None
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
Type: VMNetworkAdapter[]
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.HyperV.PowerShell.VMNetworkAdapterFailoverSetting

## NOTES

## RELATED LINKS

