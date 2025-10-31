---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hyper-v/add-vmnetworkadapter?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-VMNetworkAdapter
---

# Add-VMNetworkAdapter

## SYNOPSIS
Adds a virtual network adapter to a virtual machine.

## SYNTAX

### VMName (Default)
```
Add-VMNetworkAdapter [-CimSession <CimSession[]>] [-ComputerName <String[]>] [-Credential <PSCredential[]>]
 [-VMName] <String[]> [-SwitchName <String>] [-IsLegacy <Boolean>] [-Name <String>] [-DynamicMacAddress]
 [-StaticMacAddress <String>] [-Passthru] [-ResourcePoolName <String>] [-DeviceNaming <OnOffState>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### ManagementOS
```
Add-VMNetworkAdapter [-CimSession <CimSession[]>] [-ComputerName <String[]>] [-Credential <PSCredential[]>]
 [-ManagementOS] [-SwitchName <String>] [-Name <String>] [-DynamicMacAddress] [-StaticMacAddress <String>]
 [-Passthru] [-DeviceNaming <OnOffState>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### VMObject
```
Add-VMNetworkAdapter [-SwitchName <String>] [-IsLegacy <Boolean>] [-Name <String>] [-DynamicMacAddress]
 [-StaticMacAddress <String>] [-Passthru] [-ResourcePoolName <String>] [-VM] <VirtualMachine[]>
 [-DeviceNaming <OnOffState>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-VMNetworkAdapter** cmdlet adds a virtual network adapter to a virtual machine.

## EXAMPLES

### Example 1
```
PS C:\> Add-VMNetworkAdapter -VMName Redmond -Name "Redmond NIC1"
```

This example adds a virtual network adapter named Redmond NIC1 to a virtual machine named Redmond.

### Example 2
```
PS C:\> Add-VMNetworkAdapter -VMName Test -SwitchName Network
```

This example adds a virtual network adapter to a virtual machine named Test and connects it to a virtual switch named Network.

### Example 3
```
PS C:\> Get-VM Test | Add-VMNetworkAdapter -IsLegacy $true -Name Bootable
```

This example uses two cmdlets and the pipeline in one command to perform the operation.

### Example 4
```
PS C:\> Add-VMNetworkAdapter -ManagementOS -Name Secondary
```

This example adds a second virtual network adapter in the management operating system.

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
Specifies one or more Hyper-V hosts on which the virtual network adapter is to be added.
NetBIOS names, IP addresses, and fully qualified domain names are allowable.
The default is the local computer.
Use localhost or a dot (.) to specify the local computer explicitly.

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

### -DeviceNaming


```yaml
Type: OnOffState
Parameter Sets: (All)
Aliases:
Accepted values: On, Off

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DynamicMacAddress
Assigns a dynamically generated MAC address to the new virtual network adapter.

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

### -IsLegacy
Specifies whether the virtual network adapter is the legacy type.

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
Specifies the management operating system.

```yaml
Type: SwitchParameter
Parameter Sets: ManagementOS
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies a name for the new virtual network adapter.
The default value is "Network Adapter."

```yaml
Type: String
Parameter Sets: (All)
Aliases: VMNetworkAdapterName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Passthru
Specifies that an object is to be passed through to be pipeline representing the network adapter to be added.
If you specify **-ManagementOS**, the object passed is a **Microsoft.HyperV.PowerShell.VMInternalNetworkAdapter**; otherwise the object passed is a **Microsoft.HyperV.PowerShell.VMNetworkAdapter**.

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

### -ResourcePoolName
Specifies the friendly name of a resource pool.

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

### -StaticMacAddress
Assigns a specific MAC address to the new virtual network adapter.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SwitchName
Specifies the name of the virtual switch to connect to the new network adapter.
If the switch name is not unique, then the operation fails.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Specifies the virtual machine on which the network adapter is to be added.

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
Specifies the name of the virtual machine on which the network adapter is to be added.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### None

By default, this cmdlet doesn't return any output.

### Microsoft.HyperV.PowerShell.VMNetworkAdapter

If **PassThru** is specified, a **Microsoft.HyperV.PowerShell.VMNetworkAdapter** object is output by default.

### Microsoft.HyperV.PowerShell.VMInternalNetworkAdapter

If **PassThru** and **ManagementOS** is specified, then **Microsoft.HyperV.PowerShell.VMInternalNetworkAdapter** is output.

## NOTES

## RELATED LINKS

