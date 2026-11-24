---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NetEventVmSwitch.cdxml-help.xml
Module Name: NetEventPacketCapture
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/neteventpacketcapture/remove-neteventvmswitch?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-NetEventVmSwitch
---

# Remove-NetEventVmSwitch

## SYNOPSIS
Removes Hyper-V virtual switches from a provider.

## SYNTAX

### ByName
```
Remove-NetEventVmSwitch [-Name] <String[]> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject (cdxml)
```
Remove-NetEventVmSwitch -InputObject <CimInstance[]> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-NetEventVmSwitch** cmdlet removes Hyper-V virtual switches and the settings for the virtual switches from a Remote Packet Capture provider.
You can specify the names of Hyper-V virtual switches, or use the **InputObject** parameter to specify a **NetEventVmSwitch** object to remove.
To obtain a **NetEventVmSwitch** object, use the Get-NetEventVmSwitch cmdlet.
When you remove a Hyper-V virtual switch, the Remote Packet Capture provider no longer uses the Hyper-V virtual switch to capture event packets.

The protocol stack uses multiple layers to transmit, receive, and process network traffic as packets.
The provider logs network traffic as Event Tracing for Windows (ETW) events.

## EXAMPLES

### Example 1: Remove a Hyper-V virtual switch from a provider
```
PS C:\>New-NetEventSession -Name "NESession01"
PS C:\> Add-NetEventPacketCaptureProvider -SessionName "NESession01"
PS C:\> Add-NetEventVMSwitch -Name "Network Adapter 2 - Virtual Switch"
PS C:\> Remove-NetEventVMSwitch -Name "Network Adapter 2 - Virtual Switch"
```

This example removes a Hyper-V virtual switch from the Remote Packet Capture for a network session.

The first command uses New-NetEventSession the creates the network session named NESession01.

The second command uses the Add-NetEventPacketCaptureProvider cmdlet to add a Remote Packet Capture provider for the session named NESession01.

The third command uses the Add-NetEventVmSwitch cmdlet to add the Hyper-V virtual switch named Network Adapter 2 - Virtual Switch as a filter on the Remote Packet Capture provider.

The fourth command removes the Hyper-V virtual switch named Network Adapter 2 - Virtual Switch from the provider.

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
Specifies an array of names of Hyper-V virtual switches to remove.

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

[Get-NetEventVmSwitch](./Get-NetEventVmSwitch.md)

[Add-NetEventVmSwitch](./Add-NetEventVmSwitch.md)

