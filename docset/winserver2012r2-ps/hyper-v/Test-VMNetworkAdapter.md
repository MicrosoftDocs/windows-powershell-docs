---
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
Module Name: Hyper-V
ms.date: 10/30/2017
online version: https://docs.microsoft.com/powershell/module/hyper-v/test-vmnetworkadapter?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Test-VMNetworkAdapter
---

# Test-VMNetworkAdapter

## SYNOPSIS
Tests connectivity between virtual machines.

## SYNTAX

### VMName (Default)
```
Test-VMNetworkAdapter [-VMName] <String> [-Name <String>] [-Sender] [-Receiver] -SenderIPAddress <String>
 -ReceiverIPAddress <String> [-NextHopMacAddress <String>] [-IsolationId <Int32>] -SequenceNumber <Int32>
 [-Passthru] [-ComputerName <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ResourceObject
```
Test-VMNetworkAdapter [-VMNetworkAdapter] <VMNetworkAdapterBase> [-Sender] [-Receiver]
 -SenderIPAddress <String> -ReceiverIPAddress <String> [-NextHopMacAddress <String>] [-IsolationId <Int32>]
 -SequenceNumber <Int32> [-Passthru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### VMObject
```
Test-VMNetworkAdapter [-VM] <VirtualMachine> [-Name <String>] [-Sender] [-Receiver] -SenderIPAddress <String>
 -ReceiverIPAddress <String> [-NextHopMacAddress <String>] [-IsolationId <Int32>] -SequenceNumber <Int32>
 [-Passthru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ManagementOS
```
Test-VMNetworkAdapter [-Name <String>] -SenderIPAddress <String> -ReceiverIPAddress <String>
 [-NextHopMacAddress <String>] [-IsolationId <Int32>] -SequenceNumber <Int32> [-Passthru]
 [-ComputerName <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Test-VMNetworkAdapter** cmdlet tests connectivity between virtual machines by using Internet Control Message Protocol (ICMP) Ping packets.
Ping verifies IP-level connectivity to another TCP/IP computer by sending ICMP Echo Request messages.

## EXAMPLES

### Example 1: Test connectivity
```
PS C:\>Test-VMNetworkAdapter -VMName "ContosoVM01" -Receiver -SenderIPAddress "10.20.20.5" -ReceiverIPAddress "10.20.20.6" -VMNetworkAdapterName "ContosoNic01"
```

This command tests connectivity by using the virtual network adapter named ContosoNic01.
The command targets the receiver virtual machine.

## PARAMETERS

### -ComputerName
Specifies an array of Hyper-V hosts.
The cmdlet tests connectivity for virtual machines hosted by the computers that you specify.

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

### -IsolationId
Specifies an ID of a virtual subnet.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the virtual machine.

```yaml
Type: String
Parameter Sets: VMName, VMObject, ManagementOS
Aliases: VMNetworkAdapterName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NextHopMacAddress
Specified the MAC address for the next hop VM required for non-HNV (non Hyper-V Network Virtualization) configurations.

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

### -Receiver
Indicates that the cmdlet targets the receiver virtual machine.

```yaml
Type: SwitchParameter
Parameter Sets: VMName, ResourceObject, VMObject
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReceiverIPAddress
Specifies the IP address of the receiver virtual machine.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Sender
Indicates that the cmdlet targets the sender virtual machine.

```yaml
Type: SwitchParameter
Parameter Sets: VMName, ResourceObject, VMObject
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SenderIPAddress
Specifies the IP address of the sender virtual machine.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SequenceNumber
Specifies the sequence number to use to generate ICMP Ping packets.
The default value is 100.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Specifies a virtual machine.
The cmdlet tests connectivity for adapters that belong to the virtual machines that you specify.

```yaml
Type: VirtualMachine
Parameter Sets: VMObject
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMName
Specifies the name of a virtual machine.

```yaml
Type: String
Parameter Sets: VMName
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMNetworkAdapter
Specifies a virtual machine network adapter as a **VMNetworkAdapterBase** object.
The cmdlet tests connectivity for the adapters that you specify.
To obtain a network adapter, use the Get-VMNetworkAdapter cmdlet.

```yaml
Type: VMNetworkAdapterBase
Parameter Sets: ResourceObject
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-VMNetworkAdapter](./Add-VMNetworkAdapter.md)

[Connect-VMNetworkAdapter](./Connect-VMNetworkAdapter.md)

[Disconnect-VMNetworkAdapter](./Disconnect-VMNetworkAdapter.md)

[Get-VMNetworkAdapter](./Get-VMNetworkAdapter.md)

[Remove-VMNetworkAdapter](./Remove-VMNetworkAdapter.md)

[Rename-VMNetworkAdapter](./Rename-VMNetworkAdapter.md)

[Set-VMNetworkAdapter](./Set-VMNetworkAdapter.md)

