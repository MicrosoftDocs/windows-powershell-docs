---
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
Module Name: Hyper-V
ms.date: 10/30/2017
online version: https://docs.microsoft.com/powershell/module/hyper-v/remove-vmnetworkadapterextendedacl?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-VMNetworkAdapterExtendedAcl
---

# Remove-VMNetworkAdapterExtendedAcl

## SYNOPSIS
Removes an extended ACL for a virtual network adapter.

## SYNTAX

### VMName (Default)
```
Remove-VMNetworkAdapterExtendedAcl -Weight <Int32> -Direction <VMNetworkAdapterExtendedAclDirection>
 [-Passthru] [-VMNetworkAdapterName <String>] [-ComputerName <String[]>] [-VMName] <String[]> [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### InputObjectParameter
```
Remove-VMNetworkAdapterExtendedAcl [-InputObject] <VMNetworkAdapterExtendedAclSetting[]> [-Passthru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### VMObject
```
Remove-VMNetworkAdapterExtendedAcl -Weight <Int32> -Direction <VMNetworkAdapterExtendedAclDirection>
 [-Passthru] [-VMNetworkAdapterName <String>] [-VM] <VirtualMachine[]> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ResourceObject
```
Remove-VMNetworkAdapterExtendedAcl -Weight <Int32> -Direction <VMNetworkAdapterExtendedAclDirection>
 [-Passthru] [-VMNetworkAdapter] <VMNetworkAdapterBase[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ManagementOS
```
Remove-VMNetworkAdapterExtendedAcl -Weight <Int32> -Direction <VMNetworkAdapterExtendedAclDirection>
 [-Passthru] [-ManagementOS] [-VMNetworkAdapterName <String>] [-ComputerName <String[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-VMNetworkAdapterExtendedAcl** cmdlet removes an extended access control list (ACL) for a virtual network adapter.

## EXAMPLES

### Example 1: Remove a specific ACL
```
PS C:\> Remove-VMNetworkAdapterExtendedAcl -VMName "TSQA01" -Direction InBound -Weight 50
```

This command removes the ACL for inbound traffic that has a weight of 50 from the virtual machine named TSQA01.

### Example 2: Remove all ACLs
```
PS C:\> Get-VMNetworkAdapterExtendedAcl -VMName "TSQA01" | Remove-VMNetworkAdapterExtendedAcl
```

This command uses the Get-VMNetworkAdapterExtendedAcl cmdlet to get all the ACLs for the virtual machine named TSQA01, and then passes them to the current cmdlet by using the pipeline operator.
The command removes all the ACLs.

## PARAMETERS

### -ComputerName
Specifies an array of Hyper-V hosts.
The cmdlet removes an ACL associated with a virtual network adapter on the Hyper-V hosts that you specify.

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

### -Direction
Specifies the direction of network traffic, from the perspective of the virtual machine, to which the ACL applies.
The cmdlet removes an ACL that has the value that you specify.
The acceptable values for this parameter are:

     -- Inbound

     -- Outbound

```yaml
Type: VMNetworkAdapterExtendedAclDirection
Parameter Sets: VMName, VMObject, ResourceObject, ManagementOS
Aliases: 
Accepted values: Inbound, Outbound

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the input to this cmdlet.
You can use this parameter, or you can pipe the input to this cmdlet.

```yaml
Type: VMNetworkAdapterExtendedAclSetting[]
Parameter Sets: InputObjectParameter
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -ManagementOS
Indicates that the cmdlet operates on the parent or host operating system.
If you specify this parameter, this cmdlet removes an ACL that applies in the parent or host operating system.

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

### -Passthru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

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

### -VM
Specifies an array of virtual machines as **VirtualMachine** objects.
The cmdlet removes an ACL for network adapters that belong to the virtual machines that you specify.
To obtain a virtual machine object, use the Get-VM cmdlet.

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
The cmdlet removes an ACL for network adapters that belong to the virtual machines that you specify.

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
Specifies an array virtual machine network adapters as **VMNetworkAdapterBase** objects.
The cmdlet removes an ACL for the network adapters that you specify.
To obtain a network adapter, use the Get-VMNetworkAdapter cmdlet.

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
The cmdlet removes an ACL for the network adapter that you specify.

```yaml
Type: String
Parameter Sets: VMName, VMObject, ManagementOS
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Weight
Specifies the weight of an ACL entry.
Because weight is unique for each entry, if you specify a value for this parameter, the cmdlet removes a specific extended ACL entry.

```yaml
Type: Int32
Parameter Sets: VMName, VMObject, ResourceObject, ManagementOS
Aliases: 

Required: True
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.HyperV.PowerShell.VMNetworkAdapterExtendedAclSetting

## NOTES

## RELATED LINKS

[Add-VMNetworkAdapterExtendedAcl](./Add-VMNetworkAdapterExtendedAcl.md)

[Get-VMNetworkAdapterExtendedAcl](./Get-VMNetworkAdapterExtendedAcl.md)

[Get-VM](./Get-VM.md)

[Get-VMNetworkAdapter](./Get-VMNetworkAdapter.md)

