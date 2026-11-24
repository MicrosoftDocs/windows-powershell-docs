---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: TestDtc.psm1-help.xml
Module Name: MsDtc
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/msdtc/test-dtc?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Test-Dtc
---

# Test-Dtc

## SYNOPSIS
Tests whether two computers can participate in networked transactions.

## SYNTAX

```
Test-Dtc [[-LocalComputerName] <String>] [[-RemoteComputerName] <String>] [[-ResourceManagerPort] <Int32>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Test-Dtc** cmdlet tests whether two computers can participate in networked transactions.
The cmdlet performs the following tests:

- Checks whether the required firewall rules are enabled.
- Checks whether the Microsoft Distributed Transaction Coordinator (MSDTC) network security settings are correctly configured for network transactions.
- Checks whether the two computers can ping each other.
- Checks whether a transaction can be propagated between the two computers.

To run this cmdlet, you must first enable the firewall rule for Distributed Transaction Coordinator on both computers by using the Netsh utility run the following command:

`netsh advfirewall firewall set rule group="Distributed Transaction Coordinator" new enable=yes`

For more information, see [Netsh Command Syntax, Contexts, and Formatting](/windows-server/networking/technologies/netsh/netsh-contexts).

To enable the rule using PowerShell run the following command:

`Enable-NetFirewallRule -DisplayGroup "Distributed Transaction Coordinator"`

## EXAMPLES

### Example 1: Test MSDTC on the local computer
```
PS C:\> Test-Dtc -LocalComputerName "$env:COMPUTERNAME" -Verbose
VERBOSE: ": Firewall rule for "RPC Endpoint Mapper" is enabled."
VERBOSE: ": Firewall rule for "DTC incoming connections" is enabled."
VERBOSE: ": Firewall rule for "DTC outgoing connections" is enabled."
VERBOSE: Contoso089: AuthenticationLevel: Mutual
VERBOSE: Contoso089: InboundTransactionsEnabled: True
VERBOSE: Contoso089: OutboundTransactionsEnabled: True
VERBOSE: Contoso089: RemoteClientAccessEnabled: False
VERBOSE: Contoso089: RemoteAdministrationAccessEnabled: True
VERBOSE: Contoso089: XATransactionsEnabled: True
VERBOSE: Contoso089: LUTransactionsEnabled: True
```

This command tests MSDTC on the local computer.

### Example 2: Test MSDTC on the local computer and a remote computer
```
PS C:\> Test-Dtc -LocalComputerName "$env:COMPUTERNAME" -RemoteComputerName "Contoso075" -ResourceManagerPort 17100 -Verbose
VERBOSE: ": Firewall rule for "RPC Endpoint Mapper" is enabled."
VERBOSE: ": Firewall rule for "DTC incoming connections" is enabled."
VERBOSE: ": Firewall rule for "DTC outgoing connections" is enabled."
VERBOSE: Contoso089: AuthenticationLevel: Mutual
VERBOSE: Contoso089: InboundTransactionsEnabled: True
VERBOSE: Contoso089: OutboundTransactionsEnabled: True
VERBOSE: Contoso089: RemoteClientAccessEnabled: False
VERBOSE: Contoso089: RemoteAdministrationAccessEnabled: True
VERBOSE: Contoso089: XATransactionsEnabled: True
VERBOSE: Contoso089: LUTransactionsEnabled: True
VERBOSE: Exporting cmdlet 'Get-CimInstance'.
VERBOSE: Exporting cmdlet 'Get-CimSession'.
VERBOSE: Exporting cmdlet 'New-CimSession'.
VERBOSE: Exporting cmdlet 'New-CimSessionOption'.
VERBOSE: Exporting cmdlet 'Remove-CimSession'.
VERBOSE: Exporting cmdlet 'Get-CimAssociatedInstance'.
VERBOSE: Exporting cmdlet 'Get-CimClass'.
VERBOSE: Exporting cmdlet 'Invoke-CimMethod'.
VERBOSE: Exporting cmdlet 'New-CimInstance'.
VERBOSE: Exporting cmdlet 'Register-CimIndicationEvent'.
VERBOSE: Exporting cmdlet 'Remove-CimInstance'.
VERBOSE: Exporting cmdlet 'Set-CimInstance'.
VERBOSE: Importing cmdlet 'Get-CimAssociatedInstance'.
VERBOSE: Importing cmdlet 'Get-CimClass'.
VERBOSE: Importing cmdlet 'Get-CimInstance'.
VERBOSE: Importing cmdlet 'Get-CimSession'.
VERBOSE: Importing cmdlet 'Invoke-CimMethod'.
VERBOSE: Importing cmdlet 'New-CimInstance'.
VERBOSE: Importing cmdlet 'New-CimSession'.
VERBOSE: Importing cmdlet 'New-CimSessionOption'.
VERBOSE: Importing cmdlet 'Register-CimIndicationEvent'. "
VERBOSE: Importing cmdlet 'Remove-CimInstance'.
VERBOSE: Importing cmdlet 'Remove-CimSession'.
VERBOSE: Importing cmdlet 'Set-CimInstance'.
VERBOSE: "Contoso075 Operating System Version: 6.2.8179."
VERBOSE: "Contoso075: Firewall rule for "RPC Endpoint Mapper" is enabled."
VERBOSE: "Contoso075: Firewall rule for "DTC incoming connections" is enabled."
VERBOSE: "Contoso075: Firewall rule for "DTC outgoing connections" is enabled."
VERBOSE: Contoso075: AuthenticationLevel: Mutual
VERBOSE: Contoso075: InboundTransactionsEnabled: True
VERBOSE: Contoso075: OutboundTransactionsEnabled: True
VERBOSE: Contoso075: RemoteClientAccessEnabled: False
VERBOSE: Contoso075: RemoteAdministrationAccessEnabled: True
VERBOSE: Contoso075: XATransactionsEnabled: True
VERBOSE: Contoso075: LUTransactionsEnabled: True
VERBOSE: "Pinging computer Contoso089 from Contoso075 succeeded."
VERBOSE: "Pinging computer Contoso075 from Contoso089 succeeded."
VERBOSE: Contoso089: OleTx: a9f3f4c0-cc24-4f34-bfc3-6b6d819dab84
VERBOSE: Contoso075: OleTx: 94a24f8a-3040-4fa2-9f27-833ffb2037bc
VERBOSE: Contoso089: XA: f35da6a2-26d2-4d14-98e6-1a8feea41bc8
VERBOSE: Contoso075: XA: 15614187-293b-4a39-92ce-6740b1ea526c
VERBOSE: Contoso089: UIS: 7f8d8ad0-7096-47fd-9aab-5d561852c93b
VERBOSE: Contoso075: UIS: e1a97aaa-003c-4b61-a978-8601e8438d5f
VERBOSE: "This diagnostic test will attempt to carry out a transaction propagation between Contoso089 and
Contoso075. It requires that a TCP port is opened on Contoso089 so that a Test Resource Manager can participate
in network transactions." "You have specified 17100 as the 'ResourceManagerPort'." "Please open port 17100 in the
firewall to proceed with the test."
VERBOSE: "Test resource manager started."
VERBOSE: "A new PSSession to Contoso075 created."
VERBOSE: "Transaction propagated from Contoso089 to Contoso075 using PULL propagation."
VERBOSE: "Transaction propagated from Contoso089 to Contoso075 using PUSH propagation."
VERBOSE: "Test Resource Manager Verbose Log:"
VERBOSE: DtcDiagRM:17100 is now listening at http://Contoso089:17100/DTCDiagRM.
VERBOSE: Resolution of IP address to hostname failed, just using IP address: 2001:0db8:2a:1006:c041:b365:30de:b2e3.
VERBOSE: DtcDiagRM:17100 received a request for PropagationToken from 2001:0db8:2a:1006:c041:b365:30de:b2e3.
VERBOSE: DtcDiagRM:17100 created Transaction 4a546251-db38-4fe9-91bb-22e532deb68b.
VERBOSE: DtcDiagRM:17100 obtained a PropagationToken for Transaction 4a546251-db38-4fe9-91bb-22e532deb68b from DTC.
VERBOSE: Resolution of IP address to hostname failed, just using IP address: 2001:0db8:2a:1006:c041:b365:30de:b2e3.
VERBOSE: ResourceManager DtcDiagRM:17100 received a request for an ExportCookie from
2001:0db8:2a:1006:c041:b365:30de:b2e3.
VERBOSE: DtcDiagRM:17100 created Transaction cc088777-03c6-43cc-83f6-06539b83e1fd.
VERBOSE: DtcDiagRM:17100 obtained an ExportCookie for Transaction cc088777-03c6-43cc-83f6-06539b83e1fd from DTC.
VERBOSE: Resource Manager DtcDiagRM:17100 - 24aeb805-7ef5-4410-9a19-f5fddf93c4d2 is removed.
```

This command tests the local computer and the computer named Contoso075.
The command specifies a resource manager port.

### Example 3: Test MSDTC on a local computer that blocks inbound transactions
```
PS C:\> Test-Dtc -LocalComputerName "$env:COMPUTERNAME" -RemoteComputerName "Contoso075" -ResourceManagerPort 17100 -Verbose
VERBOSE: ": Firewall rule for "RPC Endpoint Mapper" is enabled."
VERBOSE: ": Firewall rule for "DTC incoming connections" is enabled."
VERBOSE: ": Firewall rule for "DTC outgoing connections" is enabled."
VERBOSE: Contoso089: AuthenticationLevel: Mutual
VERBOSE: Contoso089: InboundTransactionsEnabled: False
WARNING: "Contoso089: Inbound transactions are not allowed and this computer cannot participate in network transactions."
VERBOSE: Contoso089: OutboundTransactionsEnabled: True
VERBOSE: Contoso089: RemoteClientAccessEnabled: False
VERBOSE: Contoso089: RemoteAdministrationAccessEnabled: True
VERBOSE: Contoso089: XATransactionsEnabled: True
VERBOSE: Contoso089: LUTransactionsEnabled: True
VERBOSE: Operation '' complete.
VERBOSE: "Contoso075 Operating System Version: 6.2.8179."
VERBOSE: "Contoso075: Firewall rule for "RPC Endpoint Mapper" is enabled."
VERBOSE: "Contoso075: Firewall rule for "DTC incoming connections" is enabled."
VERBOSE: "Contoso075: Firewall rule for "DTC outgoing connections" is enabled."
VERBOSE: Contoso075: AuthenticationLevel: Mutual
VERBOSE: Contoso075: InboundTransactionsEnabled: True
VERBOSE: Contoso075: OutboundTransactionsEnabled: True
VERBOSE: Contoso075: RemoteClientAccessEnabled: False
VERBOSE: Contoso075: RemoteAdministrationAccessEnabled: True
VERBOSE: Contoso075: XATransactionsEnabled: True
VERBOSE: Contoso075: LUTransactionsEnabled: True
VERBOSE: "Pinging computer Contoso089 from Contoso075 succeeded."
VERBOSE: "Pinging computer Contoso075 from Contoso089 succeeded."
VERBOSE: Contoso089: OleTx: a9f3f4c0-cc24-4f34-bfc3-6b6d819dab84
VERBOSE: Contoso075: OleTx: 94a24f8a-3040-4fa2-9f27-833ffb2037bc
VERBOSE: Contoso089: XA: f35da6a2-26d2-4d14-98e6-1a8feea41bc8
VERBOSE: Contoso075: XA: 15614187-293b-4a39-92ce-6740b1ea526c
VERBOSE: Contoso089: UIS: 7f8d8ad0-7096-47fd-9aab-5d561852c93b
VERBOSE: Contoso075: UIS: e1a97aaa-003c-4b61-a978-8601e8438d5f
"DTC security settings and firewall settings should be fixed in order to complete the transactions propagation test."
```

This command tests the local computer and the computer named Contoso075.
The output from this test shows that the local computer does not allow inbound transactions.

### Example 4: Test MSDTC on a local computer that blocks outbound transactions
```
PS C:\> Test-Dtc -LocalComputerName "$env:COMPUTERNAME" -RemoteComputerName "Contoso075" -ResourceManagerPort 17100 -Verbose
VERBOSE: ": Firewall rule for "RPC Endpoint Mapper" is enabled."
VERBOSE: ": Firewall rule for "DTC incoming connections" is enabled."
VERBOSE: ": Firewall rule for "DTC outgoing connections" is enabled."
VERBOSE: Contoso089: AuthenticationLevel: Mutual
VERBOSE: Contoso089: InboundTransactionsEnabled: True
VERBOSE: Contoso089: OutboundTransactionsEnabled: False
WARNING: "Contoso089: Outbound transactions are not allowed and this computer cannot participate in network transactions."
VERBOSE: Contoso089: RemoteClientAccessEnabled: False
VERBOSE: Contoso089: RemoteAdministrationAccessEnabled: True
VERBOSE: Contoso089: XATransactionsEnabled: True
VERBOSE: Contoso089: LUTransactionsEnabled: True
VERBOSE: Operation '' complete.
VERBOSE: "Contoso075 Operating System Version: 6.2.8179."
VERBOSE: "Contoso075: Firewall rule for "RPC Endpoint Mapper" is enabled."
VERBOSE: "Contoso075: Firewall rule for "DTC incoming connections" is enabled."
VERBOSE: "Contoso075: Firewall rule for "DTC outgoing connections" is enabled."
VERBOSE: Contoso075: AuthenticationLevel: Mutual
VERBOSE: Contoso075: InboundTransactionsEnabled: True
VERBOSE: Contoso075: OutboundTransactionsEnabled: True
VERBOSE: Contoso075: RemoteClientAccessEnabled: False
VERBOSE: Contoso075: RemoteAdministrationAccessEnabled: True
VERBOSE: Contoso075: XATransactionsEnabled: True
VERBOSE: Contoso075: LUTransactionsEnabled: True
VERBOSE: "Pinging computer Contoso089 from Contoso075 succeeded."
VERBOSE: "Pinging computer Contoso075 from Contoso089 succeeded."
VERBOSE: Contoso089: OleTx: a9f3f4c0-cc24-4f34-bfc3-6b6d819dab84
VERBOSE: Contoso075: OleTx: 94a24f8a-3040-4fa2-9f27-833ffb2037bc
VERBOSE: Contoso089: XA: f35da6a2-26d2-4d14-98e6-1a8feea41bc8
VERBOSE: Contoso075: XA: 15614187-293b-4a39-92ce-6740b1ea526c
VERBOSE: Contoso089: UIS: 7f8d8ad0-7096-47fd-9aab-5d561852c93b
VERBOSE: Contoso075: UIS: e1a97aaa-003c-4b61-a978-8601e8438d5f
"DTC security settings and firewall settings should be fixed in order to complete the transactions propagation test."
```

This command tests the local computer and the computer named Contoso075.
The output from this test shows that the local computer does not allow outbound transactions.

## PARAMETERS

### -LocalComputerName
Specifies the virtual server name of the MSDTC instance on the local computer to test.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoteComputerName
Specifies the virtual server name of the MSDTC instance on the remote computer to test.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceManagerPort
Specifies the port number that the MSDTC diagnostic Resource Manager uses.
If you do not specify a value, this cmdlet uses a default value of 3002.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-Dtc](./Get-Dtc.md)

[Install-Dtc](./Install-Dtc.md)

[Start-Dtc](./Start-Dtc.md)

[Stop-Dtc](./Stop-Dtc.md)

[Uninstall-Dtc](./Uninstall-Dtc.md)
