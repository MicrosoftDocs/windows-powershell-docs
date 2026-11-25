---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NetEventVmSwitch.cdxml-help.xml
Module Name: NetEventPacketCapture
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/neteventpacketcapture/get-neteventvmswitch?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NetEventVmSwitch
---

# Get-NetEventVmSwitch

## SYNOPSIS
Gets Hyper-V virtual switches from a provider.

## SYNTAX

### ByName (Default)
```
Get-NetEventVmSwitch [[-Name] <String[]>] [-ShowInstalled] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByProviderOfTarget
```
Get-NetEventVmSwitch [-AssociatedPacketCaptureProvider <CimInstance>] [-ShowInstalled]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-NetEventVmSwitch** cmdlet gets Hyper-V virtual switches from a Remote Packet Capture provider.
This cmdlet returns a list of Hyper-V virtual switches that you configured as filters on a Remote Packet Capture provider.

The protocol stack uses multiple layers to transmit, receive, and process network traffic as packets.
The provider logs network traffic as Event Tracing for Windows (ETW) events.

## EXAMPLES

### Example 1: Get a Hyper-V virtual switch from a provider
```
PS C:\>New-NetEventSession -Name "NESession01"
PS C:\> Add-NetEventPacketCaptureProvider -SessionName "NESession01"
PS C:\> Add-NetEventVMSwitch -Name "Network Adapter 2 - Virtual Switch"
PS C:\> Add-NetEventVMSwitch -Name "Network Adapter 4 - Virtual Switch"
PS C:\> Get-NetEventVMSwitch -Name "Network Adapter 2 - Virtual Switch"
```

This example gets a Hyper-V virtual switch from the Remote Packet Capture provider for a network session.
After you complete these commands to configure the network session, you can start and stop the event and packet capture for the network session by using the Start-NetEventSession and Stop-NetEventSession cmdlets.

The first command uses the New-NetEventSession cmdlet to create a network session named NESession01.

The second command uses the Add-NetEventPacketCaptureProvider cmdlet to add a Remote Packet Capture provider for the session named NESession01.

The third command uses the Add-NetEventVmSwitch cmdlet to add the Hyper-V virtual switch named Network Adapter 2 - Virtual Switch as a filter on the Remote Packet Capture provider.

The fourth command uses the Add-NetEventVmSwitch cmdlet to add the Hyper-V virtual switch named Network Adapter 4 - Virtual Switch as a filter on the Remote Packet Capture provider.

The fifth command gets the Hyper-V virtual switch named Network Adapter 2 - Virtual Switch from the provider.

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
Specifies an array of Hyper-V virtual switches.

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

[Add-NetEventVmSwitch](./Add-NetEventVmSwitch.md)

[Remove-NetEventVmSwitch](./Remove-NetEventVmSwitch.md)

[Get-NetEventPacketCaptureProvider](./Get-NetEventPacketCaptureProvider.md)

