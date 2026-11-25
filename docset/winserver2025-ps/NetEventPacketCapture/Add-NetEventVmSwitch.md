---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NetEventVmSwitch.cdxml-help.xml
Module Name: NetEventPacketCapture
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/neteventpacketcapture/add-neteventvmswitch?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-NetEventVmSwitch
---

# Add-NetEventVmSwitch

## SYNOPSIS
Adds a Hyper-V virtual switch as a filter on a provider.

## SYNTAX

```
Add-NetEventVmSwitch [-Name] <String> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-NetEventVmSwitch** cmdlet adds a Hyper-V virtual switch as a filter on a Remote Packet Capture provider.
Use this cmdlet multiple times to add multiple Hyper-V virtual switches.
To get existing Hyper-V virtual switches, use the Get-NetEventVmSwitch cmdlet.

The protocol stack uses multiple layers to transmit, receive, and process network traffic as packets.
The provider logs network traffic as Event Tracing for Windows (ETW) events.

## EXAMPLES

### Example 1: Add a Hyper-V virtual switch on a provider
```
PS C:\>New-NetEventSession -Name "NESession01"
PS C:\> Add-NetEventPacketCaptureProvider -SessionName "NESession01"
PS C:\> Add-NetEventVMSwitch -Name "Network Adapter 2 - Virtual Switch"
```

This example adds a Hyper-V virtual switch as a filter on the Remote Packet Capture provider for a network session.
After you complete these commands to configure the network session, you can start and stop the event and packet capture for the network session by using the Start-NetEventSession and Stop-NetEventSession cmdlets.

The first command uses the New-NetEventSession cmdlet to create a network session named NESession01.

The second command uses the Add-NetEventPacketCaptureProvider cmdlet to add a Remote Packet Capture provider for the session named NESession01.

The third command adds a Hyper-V virtual switch as a filter on the Remote Packet Capture provider.

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
Specifies a name for the Hyper-V virtual switch.

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

[Get-NetEventVmSwitch](./Get-NetEventVmSwitch.md)

[Remove-NetEventVmSwitch](./Remove-NetEventVmSwitch.md)

