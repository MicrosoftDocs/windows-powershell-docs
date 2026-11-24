---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NetEventNetworkAdapter.cdxml-help.xml
Module Name: NetEventPacketCapture
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/neteventpacketcapture/get-neteventnetworkadapter?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NetEventNetworkAdapter
---

# Get-NetEventNetworkAdapter

## SYNOPSIS
Gets the network adapters associated with a Remote Packet Capture provider.

## SYNTAX

### ByName (Default)
```
Get-NetEventNetworkAdapter [[-Name] <String[]>] [-ShowInstalled] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByProviderOfTarget
```
Get-NetEventNetworkAdapter [-AssociatedPacketCaptureProvider <CimInstance>] [-ShowInstalled]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-NetEventNetworkAdapter** cmdlet gets the network adapters associated with a Remote Packet Capture provider for a network event session.
The protocol stack uses multiple layers to transmit, receive, and process network traffic, or packets.
The provider logs network traffic as Event Tracing for Windows (ETW) events.

Use the Add-NetEventNetworkAdapter cmdlet to add an adapter or the Remove-NetEventNetworkAdapter cmdlet to remove an adapter.

## EXAMPLES

### Example 1: Get all network adapters
```
PS C:\>Get-NetEventNetworkAdapter
```

This command gets all the network adapters for the Remote Packet Capture provider for the current session.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

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

### -AssociatedPacketCaptureProvider
Specifies the associated packet capture provider as a CIM object.
To obtain the packet capture provider, use the Get-NetEventPacketCaptureProvider cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByProviderOfTarget
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies an array of names of network adapters to get.
If you do not specify this parameter, the cmdlet gets all the network adapters for the session.

```yaml
Type: String[]
Parameter Sets: ByName
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ShowInstalled
Indicates that the cmdlet displays all network adapters that are installed on the computer.

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

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell® calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
The throttle limit applies only to the current cmdlet, not to the session or to the computer.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-NetEventNetworkAdapter](./Add-NetEventNetworkAdapter.md)

[Remove-NetEventNetworkAdapter](./Remove-NetEventNetworkAdapter.md)

[Get-NetEventPacketCaptureProvider](./Get-NetEventPacketCaptureProvider.md)

