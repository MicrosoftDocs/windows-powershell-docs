---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NetEventWFPCaptureProvider.cdxml-help.xml
Module Name: NetEventPacketCapture
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/neteventpacketcapture/set-neteventwfpcaptureprovider?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-NetEventWFPCaptureProvider
---

# Set-NetEventWFPCaptureProvider

## SYNOPSIS
Modifies the configuration of a WFP capture provider.

## SYNTAX

### BySessionName (Default)
```
Set-NetEventWFPCaptureProvider [[-SessionName] <String[]>] [[-Level] <Byte>] [[-MatchAnyKeyword] <UInt64>]
 [[-MatchAllKeyword] <UInt64>] [[-CaptureLayerSet] <WFPCaptureSet>] [[-IPAddresses] <String[]>]
 [[-TCPPorts] <UInt16[]>] [[-UDPPorts] <UInt16[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### BySessionOfTheProvider
```
Set-NetEventWFPCaptureProvider [-AssociatedEventSession <CimInstance>] [[-Level] <Byte>]
 [[-MatchAnyKeyword] <UInt64>] [[-MatchAllKeyword] <UInt64>] [[-CaptureLayerSet] <WFPCaptureSet>]
 [[-IPAddresses] <String[]>] [[-TCPPorts] <UInt16[]>] [[-UDPPorts] <UInt16[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject (cdxml)
```
Set-NetEventWFPCaptureProvider -InputObject <CimInstance[]> [[-Level] <Byte>] [[-MatchAnyKeyword] <UInt64>]
 [[-MatchAllKeyword] <UInt64>] [[-CaptureLayerSet] <WFPCaptureSet>] [[-IPAddresses] <String[]>]
 [[-TCPPorts] <UInt16[]>] [[-UDPPorts] <UInt16[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-NetEventWFPCaptureProvider** cmdlet modifies the configuration of a Windows Firewall Platform (WFP) capture provider.
For more information about the **NetEventWFPCaptureProvider**, see the Add-NetEventWFPCaptureProvider cmdlet.

## EXAMPLES

### Example 1: Modify a WFP capture provider
```
PS C:\>New-NetEventSession -Name "WFPCapture" -CaptureMode RealtimeLocal -LocalFilePath "C:\users\DavidChew\Documents\wfpdata.etl"
PS C:\> Add-NetEventWFPCaptureProvider -SessionName "WFPCapture"
PS C:\> Set-NetEventWFPCaptureProvider -SessionName "WFPCapture" -CaptureLayerSet IPv4Inbound, IPv6Inbound -IPAddresses "127.0.0.1", "::1"
PS C:\> Start-NetEventSession -Name "WFPCapture"
PS C:\> ping 127.0.0.1
PS C:\> ping ::1
PS C:\> Stop-NetEventSession -Name "WFPCapture"
PS C:\> Remove-NetEventSession -Name "WFPCapture"
```

The first command creates a network event session by using the New-NetEventSession cmdlet.
This command also assigns the name WFPCapture to the session.

The second command uses the current cmdlet to create a WFP capture provider for the session named WFPCapture.

The third command configures the provider for capture layer directional filtering and loopback IP addresses.

The fourth command starts the session named WFPCapture.

The fifth and commands use the ping utility to test the local host address in both IPv4 and IPv6.
The provider should capture both of these local test connections.

The final two commands stop the session named WFPCapture and remove it.

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

### -CaptureLayerSet
Specifies a WFP capture set, which designates the layers and directions to filter.
The acceptable values for this parameter are:

- IPv4Inbound
- IPv4Outbound
- IPv6Inbound
- IPv6Outbound

You can logically OR the direction and IP layer pairs together.
For instance, you could capture incoming loopback traffic from IPv6 to avoid seeing duplicate traffic received by the loopback interface.

```yaml
Type: WFPCaptureSet
Parameter Sets: (All)
Aliases:
Accepted values: IPv4Inbound, IPv4Outbound, IPv6Inbound, IPv6Outbound

Required: False
Position: 3007
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

### -IPAddresses
Specifies an array of IP addresses.
The provider filters for and logs network traffic that matches the IP addresses that this parameter specifies.
The provider joins multiple addresses by using logical OR.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 3008
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the input object that is used in a pipeline command.

```yaml
Type: CimInstance[]
Parameter Sets: InputObject (cdxml)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Level
Specifies the Event Tracing for Windows (ETW) event error levels that **NetEventWFPCaptureProvider** returns.
Use a level of detail specifier as a filter the type of error events that are logged.
The default value for this parameter is 0x4, for informational events.
The acceptable values for this parameter are:

- 0x5.
Verbose
- 0x4.
Informational
- 0x3.
Warning
- 0x2.
Error
- 0x1.
Critical
- 0x0.
LogAlways

The provider must log the event if the value of the event is less than or equal to the value of this parameter.
Lower level events up to and including the specified level are logged.

```yaml
Type: Byte
Parameter Sets: (All)
Aliases:

Required: False
Position: 3003
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MatchAllKeyword
Specifies a keyword bitmask that restricts the events that the provider logs.

```yaml
Type: UInt64
Parameter Sets: (All)
Aliases:

Required: False
Position: 3005
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MatchAnyKeyword
Specifies keywords as a set of hexadecimal values.
Keywords are flags that you can combine to generate hexadecimal values that enable the provider to write one or more events for which it is instrumented, if a match is found.
Use a set of hexadecimal values for keywords instead of the keyword names, and apply a filter to write ETW events for keyword matches.
For more information, see [EnableTraceEx2 function](https://msdn.microsoft.com/en-us/library/windows/desktop/dd392305(v=vs.85)) in the Microsoft Developer Network library.

```yaml
Type: UInt64
Parameter Sets: (All)
Aliases:

Required: False
Position: 3004
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
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

### -SessionName
Specifies an array of session names that are associated with the **NetEventWFPCaptureProvider**.
This parameter has the same value as the **Name** parameter for the New-NetEventSession cmdlet.

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

### -TCPPorts
Specifies an array of TCP ports.
The provider filters and logs network traffic that matches the ports that this parameter specifies.
The provider joins multiple port numbers with logical OR.

```yaml
Type: UInt16[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 3009
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

### -UDPPorts
Specifies an array of UDP ports.
The provider filters and logs network traffic that matches the ports that this parameter specifies.
The provider joins multiple port numbers with logical OR.

```yaml
Type: UInt16[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 3010
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

[Add-NetEventWFPCaptureProvider](./Add-NetEventWFPCaptureProvider.md)

[Get-NetEventWFPCaptureProvider](./Get-NetEventWFPCaptureProvider.md)

[Remove-NetEventWFPCaptureProvider](./Remove-NetEventWFPCaptureProvider.md)

