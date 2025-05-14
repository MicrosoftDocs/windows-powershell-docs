---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Test-VirtualNetworkConnection.psm1-help.xml
Module Name: HNVDiagnostics
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hnvdiagnostics/test-virtualnetworkconnection?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Test-VirtualNetworkConnection
---

# Test-VirtualNetworkConnection

## SYNOPSIS
Tests a virtual network connection.

## SYNTAX

```
Test-VirtualNetworkConnection [-OperationId] <String> [[-HostName] <String>] [[-MgmtIp] <String>]
 [[-Creds] <PSCredential>] [[-VMName] <String>] [[-VMNetworkAdapterName] <String>]
 [[-VMNetworkAdapterProfileId] <String>] [-IsSender] <Boolean> [-SenderCAIP] <String> [-SenderVSID] <Int32>
 [-ListenerCAIP] <String> [-ListenerVSID] <Int32> [-SequenceNumber] <Int32> [[-PayloadSize] <Int32>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Test-VirtualNetworkConnection** cmdlet tests connectivity over a virtual network by sending Internet Control Message Protocol (ICMP) packets between two Customer Address IP addresses (CAIPs).
The two nodes can reside on the same virtual subnet ID (VSID), or they can share a VSID.

## EXAMPLES

### Example 1: Test a virtual network connection by sending
```
PS C:\> $cred = Get-Credential
PS C:\> Test-VirtualNetworkConnection -OperationId "27" -HostName "host1.corp.com" -MgmtIP "192.10.10.11" -Creds $creds -VMName "TennantVM1" -VMNetworkAdapterName "Tennant1VMAdapter1" -IsSender $True -SenderCAIP "10.123.176.108" -SenderVSID 6001 -ListenerCAIP "10.123.176.108" -ListenerVSID 6001 -SequenceNumber 33 -PayloadSize 1500
```

The first command gets the credentials for the current user, and then stores them in the $cred variable.

The second command tests the specified virtual network connection.

### Example 2: Test a virtual network connection by receiving
```
PS C:\> $password = ConvertTo-SecureString -String "password" -AsPlainText -Force
PS C:\> $cred = New-Object PSCredential -ArgumentList (".\administrator", $password)
PS C:\> Test-VirtualNetworkConnection -OperationId "27" -HostName "host2.corp.com" -MgmtIP "192.10.10.12" -Creds $cred -VMName "TennantVM2" -VMNetworkAdapterName "Tennant1VMAdapter2" -SenderCAIP "10.123.176.108" -SenderVSID 6001 -ListenerCAIP "10.123.176.109" -ListenerVSID 6001
```

The first command converts a plain text password to a secure string, and then stores it in the $password variable.

The second command creates a **PSCredential** object, and then stores it in the $cred variable.

The third command tests the specified virtual network connection.

## PARAMETERS

### -Creds
Specifies the credentials for Network Controller.
Specify this parameter for Kerberos deployments.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HostName
Specifies the name of the host on which to run the test.

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

### -IsSender
Indicates whether this operation is for the sender or receiver.
One of each is required.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: True
Position: 7
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ListenerCAIP
Specifies the CAIP of the listener.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 10
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ListenerVSID
Specifies the VSID on which to initiate the test.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: True
Position: 11
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MgmtIp
Specifies the IP of the management host on which to initiate the test.

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

### -OperationId
Specifies a unique ID for the test.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PayloadSize
Specifies the size of the payload to carry in ICMP messages.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: 13
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SenderCAIP
Specifies the CAIP of the sender.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 8
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SenderVSID
Specifies the VSID of the sender.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: True
Position: 9
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SequenceNumber
Specifies the sequence number to use in the ICMP packets.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: True
Position: 12
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMName
Specifies the name of a virtual machine.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMNetworkAdapterName
Specifies the name of the virtual machine with the desired CAIP.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMNetworkAdapterProfileId
Specifies the name of the adapter for the desired CAIP.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 6
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

