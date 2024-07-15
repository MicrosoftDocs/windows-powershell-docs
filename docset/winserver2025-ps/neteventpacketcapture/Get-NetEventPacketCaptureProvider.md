---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NetEventPacketCaptureProvider.cdxml-help.xml
Module Name: NetEventPacketCapture
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/neteventpacketcapture/get-neteventpacketcaptureprovider?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NetEventPacketCaptureProvider
---

# Get-NetEventPacketCaptureProvider

## SYNOPSIS
Displays a Remote Packet Capture provider.

## SYNTAX

### BySessionName (Default)
```
Get-NetEventPacketCaptureProvider [[-SessionName] <String[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### BySessionOfTheProvider
```
Get-NetEventPacketCaptureProvider [-AssociatedEventSession <CimInstance>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByTargetOfTheProvider
```
Get-NetEventPacketCaptureProvider [-AssociatedCaptureTarget <CimInstance>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-NetEventPacketCaptureProvider** cmdlet displays a Remote Packet Capture provider.

## EXAMPLES

### Example 1: Display a packet capture provider
```
PS C:\>Get-NetEventPacketCaptureProvider -SessionName "Session01"
```

This command displays a packet capture provider for a session named Session01.

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

### -AssociatedCaptureTarget
Specifies the associated capture target as a CIM object.
The capture target is one of the three following objects:

- **MSFT_NetEventNetworkAdapter**
- **MSFT_NetEventVmNetworkAdapter**
- **MSFT_NetEventVmSwitch**

To obtain a capture target, use the Get-NetEventNetworkAdapter cmdlet, the Get-NetEventVmNetworkAdapter cmdlet, or the Get-NetEventVmSwitch cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByTargetOfTheProvider
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -AssociatedEventSession
Specifies the associated network event session, as a CIM object.
To obtain the network event session, use the Get-NetEventSession cmdlet.

```yaml
Type: CimInstance
Parameter Sets: BySessionOfTheProvider
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

### -SessionName
Specifies an array of names of sessions associated with packet capture providers.

```yaml
Type: String[]
Parameter Sets: BySessionName
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
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

[Add-NetEventPacketCaptureProvider](./Add-NetEventPacketCaptureProvider.md)

[Remove-NetEventPacketCaptureProvider](./Remove-NetEventPacketCaptureProvider.md)

[Set-NetEventPacketCaptureProvider](./Set-NetEventPacketCaptureProvider.md)

[Get-NetEventNetworkAdapter](./Get-NetEventNetworkAdapter.md)

[Get-NetEventVmNetworkAdapter](./Get-NetEventVmNetworkAdapter.md)

[Get-NetEventVmSwitch](./Get-NetEventVmSwitch.md)

[Get-NetEventSession](./Get-NetEventSession.md)

