---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NetEventSession.cdxml-help.xml
Module Name: NetEventPacketCapture
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/neteventpacketcapture/start-neteventsession?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Start-NetEventSession
---

# Start-NetEventSession

## SYNOPSIS
Starts event and packet capture for a network event session.

## SYNTAX

### ByName
```
Start-NetEventSession [-Name] <String[]> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject (cdxml)
```
Start-NetEventSession -InputObject <CimInstance[]> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Start-NetEventSession** cmdlet starts event and packet capture for a network event session.
A session controls how the computer logs events and, optionally, network traffic, or packets.
Use the New-NetEventSession cmdlet to create a session.
Before you can start logging, add network event providers to a session.
A network event provider logs events and network traffic as Event Tracing for Windows (ETW) events.

If a session is currently running, you cannot start it.
Use the Get-NetEventSession cmdlet to see session status.

## EXAMPLES

### Example 1: Start a session
```
PS C:\>New-NetEventSession -Name "Session38"
PS C:\> Add-NetEventProvider -Name "Microsoft-Windows-TCPIP" -SessionName "Session38"
PS C:\> Start-NetEventSession -Name "Session38"
```

This example creates a session, adds a provider to it, and then starts the session.

The first command creates a session named Session38 by using the New-NetEventSession cmdlet.

The second command adds a provider to the session by using the Add-NetEventProvider cmdlet.
A session must have a provider in order to log events.

The third command starts the session named Session38.

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

### -Name
Specifies an array of names of sessions to start.

```yaml
Type: String[]
Parameter Sets: ByName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
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

[Get-NetEventSession](./Get-NetEventSession.md)

[New-NetEventSession](./New-NetEventSession.md)

[Remove-NetEventSession](./Remove-NetEventSession.md)

[Set-NetEventSession](./Set-NetEventSession.md)

[Stop-NetEventSession](./Stop-NetEventSession.md)

