---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NetEventSession.cdxml-help.xml
Module Name: NetEventPacketCapture
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/neteventpacketcapture/get-neteventsession?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NetEventSession
---

# Get-NetEventSession

## SYNOPSIS
Gets network event sessions.

## SYNTAX

### ByName (Default)
```
Get-NetEventSession [[-Name] <String[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByProviderOfSession
```
Get-NetEventSession [-AssociatedEventProvider <CimInstance>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-NetEventSession** cmdlet gets network event sessions.
A session controls how the computer logs events and, optionally, network traffic, or packets.

Use this cmdlet to display configuration settings for the session.
The configuration settings include the following:

- Whether the session writes logs to a local file or sends events to live display.
- For local file logging, the maximum size and location of the .etl file.
- The maximum number of buffers and size of a buffer.

You can also use this cmdlet to see whether the session is running, such as after you run the Start-NetEventSession cmdlet.

## EXAMPLES

### Example 1: Display settings for a session
```
PS C:\>Get-NetEventSession -Name "Session38"
```

This command displays the settings of the session named Session38.

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

### -AssociatedEventProvider
Specifies the associated network event provider as a CIM object.
To obtain the network event provider, use the Get-NetEventProvider cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByProviderOfSession
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
Specifies an array of names of sessions to get.

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

[New-NetEventSession](./New-NetEventSession.md)

[Remove-NetEventSession](./Remove-NetEventSession.md)

[Set-NetEventSession](./Set-NetEventSession.md)

[Start-NetEventSession](./Start-NetEventSession.md)

[Stop-NetEventSession](./Stop-NetEventSession.md)

[Get-NetEventProvider](./Get-NetEventProvider.md)

