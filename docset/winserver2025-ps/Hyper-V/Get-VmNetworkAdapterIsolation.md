---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hyper-v/get-vmnetworkadapterisolation?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-VmNetworkAdapterIsolation
---

# Get-VMNetworkAdapterIsolation

## SYNOPSIS
Gets isolation settings for a virtual network adapter.

## SYNTAX

### VMName (Default)
```
Get-VMNetworkAdapterIsolation [[-VMName] <String[]>] [-VMNetworkAdapterName <String>]
 [-CimSession <CimSession[]>] [-ComputerName <String[]>] [-Credential <PSCredential[]>] [<CommonParameters>]
```

### VMSnapshot
```
Get-VMNetworkAdapterIsolation [-VMSnapshot] <VMSnapshot> [<CommonParameters>]
```

### ResourceObject
```
Get-VMNetworkAdapterIsolation [-VMNetworkAdapter] <VMNetworkAdapterBase[]> [<CommonParameters>]
```

### ManagementOS
```
Get-VMNetworkAdapterIsolation [-ManagementOS] [-VMNetworkAdapterName <String>] [-CimSession <CimSession[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential[]>] [<CommonParameters>]
```

### VMObject
```
Get-VMNetworkAdapterIsolation [-VMNetworkAdapterName <String>] [-VM] <VirtualMachine[]> [<CommonParameters>]
```

## DESCRIPTION
The **Get-VmNetworkAdapterIsolation** cmdlet gets isolation settings for a virtual network adapter.
The cmdlet displays the isolation method, and other information, such as the multitenancy mode and the subnet ID for traffic bound for to the default compartment if multitenancy is enabled.

## EXAMPLES

### Example 1
```
PS C:\> Get-VMNetworkAdapterIsolation -VMName Multitenant-GW -VMNetworkAdapterName InternalNIC
```

This example retrieves the isolation settings of a VM.

## PARAMETERS

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: VMName, ManagementOS
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies an array of Hyper-V hosts.
The cmdlet gets isolation settings for virtual machines hosted by the computers that you specify.

```yaml
Type: String[]
Parameter Sets: VMName, ManagementOS
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
Parameter Sets: VMName, ManagementOS
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ManagementOS
Indicates that the cmdlet operates on the parent or host operating system.
If you specify this parameter, this cmdlet gets isolation settings for the parent or host operating system.

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

### -VM
Specifies an array of virtual machines.
The cmdlet gets isolation settings for adapters that belong to the virtual machines that you specify.
To obtain a virtual machine object, use the **Get-VM** cmdlet.

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
Specifies an array of names of virtual machines.
The cmdlet gets isolation settings for adapters that belong to the virtual machines that you specify.

```yaml
Type: String[]
Parameter Sets: VMName
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMNetworkAdapter
Specifies an array virtual machine network adapters as **VMNetworkAdapterBase** objects.
The cmdlet gets isolation settings for the adapters that you specify.
To obtain a network adapter, use the **Get-VMNetworkAdapter** cmdlet.

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
Specifies the name of a virtual network adapter.
The cmdlet gets isolation settings for the adapters that you specify.

```yaml
Type: String
Parameter Sets: VMName, ManagementOS, VMObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMSnapshot
Specifies a snapshot as a **VMSnapshot** object.
The cmdlet gets isolation settings for network adapters that belong to the snapshot that you specify.
To obtain a snapshot, use the **Get-VMSnapshot** cmdlet.

```yaml
Type: VMSnapshot
Parameter Sets: VMSnapshot
Aliases: VMCheckpoint

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.HyperV.PowerShell.VMNetworkAdapterIsolationSetting

## NOTES

## RELATED LINKS

[Set-VmNetworkAdapterIsolation](./Set-VmNetworkAdapterIsolation.md)

[Get-VM](./Get-VM.md)

[Get-VMSnapshot](./Get-VMSnapshot.md)

[Get-VMNetworkAdapter](./Get-VMNetworkAdapter.md)

