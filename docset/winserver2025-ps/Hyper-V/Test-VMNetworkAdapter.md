---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hyper-v/test-vmnetworkadapter?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Test-VMNetworkAdapter
---

# Test-VMNetworkAdapter

## SYNOPSIS
Tests connectivity between virtual machines.

## SYNTAX

### VMName (Default)
```
Test-VMNetworkAdapter [-CimSession <CimSession[]>] [-ComputerName <String[]>] [-Credential <PSCredential[]>]
 [-VMName] <String> [-Name <String>] [-Sender] [-Receiver] -SenderIPAddress <String>
 -ReceiverIPAddress <String> [-NextHopMacAddress <String>] [-IsolationId <Int32>] -SequenceNumber <Int32>
 [-PayloadSize <Int32>] [-Passthru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ResourceObject
```
Test-VMNetworkAdapter [-VMNetworkAdapter] <VMNetworkAdapter> [-Sender] [-Receiver] -SenderIPAddress <String>
 -ReceiverIPAddress <String> [-NextHopMacAddress <String>] [-IsolationId <Int32>] -SequenceNumber <Int32>
 [-PayloadSize <Int32>] [-Passthru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### VMObject
```
Test-VMNetworkAdapter [-VM] <VirtualMachine> [-Name <String>] [-Sender] [-Receiver] -SenderIPAddress <String>
 -ReceiverIPAddress <String> [-NextHopMacAddress <String>] [-IsolationId <Int32>] -SequenceNumber <Int32>
 [-PayloadSize <Int32>] [-Passthru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Test-VMNetworkAdapter** cmdlet tests connectivity between virtual machines by using Internet Control Message Protocol (ICMP) Ping packets.
Ping verifies IP-level connectivity to another TCP/IP computer by sending ICMP Echo Request messages.

## EXAMPLES

### Example 1: Test connectivity
```
PS C:\> Test-VMNetworkAdapter -VMName "ContosoVM01" -Receiver -SenderIPAddress "10.20.20.5" -ReceiverIPAddress "10.20.20.6" -VMNetworkAdapterName "ContosoNic01"
```

This command tests connectivity by using the virtual network adapter named ContosoNic01.
The command targets the receiver virtual machine.

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
Specifies one or more Hyper-V hosts on which this cmdlet operates.
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
Parameter Sets: VMName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IsolationId
Specifies the ID of a virtual subnet.

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
Parameter Sets: VMName, VMObject
Aliases: VMNetworkAdapterName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NextHopMacAddress
Specified the MAC address for the next hop VM required for non-Hyper-V Network Virtualization configurations.

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

### -PayloadSize


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

### -Receiver
Indicates that the cmdlet targets the receiver virtual machine.

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
Parameter Sets: (All)
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
To obtain a network adapter, use the **Get-VMNetworkAdapter** cmdlet.

```yaml
Type: VMNetworkAdapter
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.HyperV.PowerShell.VMNetworkAdapterConnectionTestResult

## NOTES

## RELATED LINKS

[Add-VMNetworkAdapter](./Add-VMNetworkAdapter.md)

[Connect-VMNetworkAdapter](./Connect-VMNetworkAdapter.md)

[Disconnect-VMNetworkAdapter](./Disconnect-VMNetworkAdapter.md)

[Get-VMNetworkAdapter](./Get-VMNetworkAdapter.md)

[Remove-VMNetworkAdapter](./Remove-VMNetworkAdapter.md)

[Rename-VMNetworkAdapter](./Rename-VMNetworkAdapter.md)

[Set-VMNetworkAdapter](./Set-VMNetworkAdapter.md)

