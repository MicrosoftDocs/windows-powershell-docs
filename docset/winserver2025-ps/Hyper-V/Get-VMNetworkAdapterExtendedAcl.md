---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hyper-v/get-vmnetworkadapterextendedacl?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-VMNetworkAdapterExtendedAcl
---

# Get-VMNetworkAdapterExtendedAcl

## SYNOPSIS
Gets extended ACLs configured for a virtual network adapter.

## SYNTAX

### VMName (Default)
```
Get-VMNetworkAdapterExtendedAcl [[-VMName] <String[]>] [-VMNetworkAdapterName <String>]
 [-CimSession <CimSession[]>] [-ComputerName <String[]>] [-Credential <PSCredential[]>] [<CommonParameters>]
```

### VMSnapshot
```
Get-VMNetworkAdapterExtendedAcl [-VMSnapshot] <VMSnapshot> [<CommonParameters>]
```

### ResourceObject
```
Get-VMNetworkAdapterExtendedAcl [-VMNetworkAdapter] <VMNetworkAdapterBase[]> [<CommonParameters>]
```

### ManagementOS
```
Get-VMNetworkAdapterExtendedAcl [-ManagementOS] [-VMNetworkAdapterName <String>] [-CimSession <CimSession[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential[]>] [<CommonParameters>]
```

### VMObject
```
Get-VMNetworkAdapterExtendedAcl [-VMNetworkAdapterName <String>] [-VM] <VirtualMachine[]> [<CommonParameters>]
```

## DESCRIPTION
The **Get-VMNetworkAdapterExtendedAcl** cmdlet gets the extended access control lists (ACLs) configured for a virtual network adapter.
If an ACL applies to both inbound and outbound packets, it appears in both inbound and outbound lists.

## EXAMPLES

### Example 1: Get all extended ACLs
```
PS C:\> Get-VMNetworkAdapterExtendedAcl -VMName "TSQA01"
```

This command gets all the extended ACLs for the virtual machine named TSQA01.

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
The cmdlet gets the ACLs associated with the virtual network adapters on the Hyper-V hosts that you specify.

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
If you specify this parameter, this cmdlet gets ACLs associated with network adapters in the parent or host operating system.

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
Specifies an array of virtual machines as **VirtualMachine** objects.
The cmdlet gets ACLs for network adapters that belong to the virtual machines that you specify.
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
Specifies an array of names of VMs.
The cmdlet gets ACLs associated with network adapters that belong to the VMs that you specify.

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
Specifies an array of virtual network adapter objects.
The cmdlet gets ACLs associated with the adapters that you specify.
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
The cmdlet gets extended ACLs associated with the adapter that you specify.

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
The cmdlet gets ACLs for network adapters that belong to the snapshot that you specify.
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

### Microsoft.HyperV.PowerShell.VMNetworkAdapterExtendedAclSetting


## NOTES

## RELATED LINKS

[Add-VMNetworkAdapterExtendedAcl](./Add-VMNetworkAdapterExtendedAcl.md)

[Remove-VMNetworkAdapterExtendedAcl](./Remove-VMNetworkAdapterExtendedAcl.md)

[Get-VM](./Get-VM.md)

[Get-VMNetworkAdapter](./Get-VMNetworkAdapter.md)

[Get-VMSnapshot](./Get-VMSnapshot.md)

