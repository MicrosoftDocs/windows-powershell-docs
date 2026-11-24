---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NetEventNetworkAdapter.cdxml-help.xml
Module Name: NetEventPacketCapture
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/neteventpacketcapture/add-neteventnetworkadapter?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-NetEventNetworkAdapter
---

# Add-NetEventNetworkAdapter

## SYNOPSIS
Adds a network adapter as a filter on a provider.

## SYNTAX

```
Add-NetEventNetworkAdapter [-Name] <String> [[-PromiscuousMode] <Boolean>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-NetEventNetworkAdapter** cmdlet adds a network adapter as a filter on a Remote Packet Capture provider.
The protocol stack uses multiple layers to transmit, receive, and process network traffic, or packets.
The provider logs network traffic as Event Tracing for Windows (ETW) events.

Use this cmdlet multiple times to add several adapters.
To see which adapters currently belong to a provider, use the Get-NetEventNetworkAdapter cmdlet.

When you add an adapter to provider in a session that is currently running, stop and start the session for your changes to take effect.
Use the Stop-NetEventSession cmdlet to stop a session and the Start-NetEventSession cmdlet to restart it.

## EXAMPLES

### Example 1: Add a network adapter
```
PS C:\>New-NetEventSession -Name "Session38"
PS C:\> Add-NetEventPacketCaptureProvider -SessionName "Session38"
PS C:\> Add-NetEventNetworkAdapter -Name "Ethernet01"
```

This example creates a network event session, adds a provider, and then adds a network adapter.

The first command uses the New-NetEventSession cmdlet to create a network event session named Session38.

The second command adds a provider to the session named Session38 by using the Add-NetEventPacketCaptureProvider cmdlet.
A session must have a provider in order to capture packets.

The third command adds a network adapter.
After you create and configure the session, use the Start-NetEventSession cmdlet to start capturing packets.

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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of a network adapter to add.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PromiscuousMode
Specifies whether the network adapter uses promiscuous mode.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
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

### -WhatIf
Shows what would happen if the cmdlet runs. The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

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

[Get-NetEventNetworkAdapter](./Get-NetEventNetworkAdapter.md)

[Remove-NetEventNetworkAdapter](./Remove-NetEventNetworkAdapter.md)

[New-NetEventSession](./New-NetEventSession.md)

[Add-NetEventPacketCaptureProvider](./Add-NetEventPacketCaptureProvider.md)

