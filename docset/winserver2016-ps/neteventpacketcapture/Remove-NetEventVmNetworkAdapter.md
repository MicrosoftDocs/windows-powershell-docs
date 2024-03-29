---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NetEventVmNetworkAdatper.cdxml-help.xml
Module Name: NetEventPacketCapture
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/neteventpacketcapture/remove-neteventvmnetworkadapter?view=windowsserver2016-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-NetEventVmNetworkAdapter
---

# Remove-NetEventVmNetworkAdapter

## SYNOPSIS
Removes virtual network adapters from a provider.

## SYNTAX

### ByName
```
Remove-NetEventVmNetworkAdapter [-Name] <String[]> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject (cdxml)
```
Remove-NetEventVmNetworkAdapter -InputObject <CimInstance[]> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-NetEventVmNetworkAdapter** cmdlet removes network adapters of a virtual machine and the settings for the adapters from a Remote Packet Capture provider.
Specify the names of the virtual network adapters, or use the **InputObject** parameter to specify a **NetEventVmNetworkAdapter** object to remove.
When you remove a virtual network adapter, the Remote Packet Capture provider no longer uses the adapter to capture event packets.

The protocol stack uses multiple layers to transmit, receive, and process network traffic as packets.
The provider logs network traffic as Event Tracing for Windows (ETW) events.

## EXAMPLES

### Example 1: Remove a virtual network adapter from the provider
```
PS C:\>New-NetEventSession -Name "NESession01"
PS C:\> Add-NetEventPacketCaptureProvider -SessionName "NESession01"
PS C:\> Add-NetEventVMNetworkAdapter -Name "LargeGuid"
PS C:\> Add-NetEventVMNetworkAdapter -Name "LargeGuid02"
PS C:\> Get-NetEventVMNetworkAdapter
```

This example removes a virtual network adapter from the Remote Packet Capture provider for a network session.
After you complete these commands to configure the network session, you can start and stop the event and packet capture for the network session by using the Start-NetEventSession and Stop-NetEventSession cmdlets.

The first command uses the New-NetEventSession cmdlet to create a network session named NESession01.

The second command uses the Add-NetEventPacketCaptureProvider cmdlet to add a Remote Packet Capture provider for the session named NESession01.

The third command uses the Add-NetEventVmSwitch cmdlet to add the virtual network adapter named LargeGuid as a filter on the Remote Packet Capture provider.

The fourth command uses the Add-NetEventVmSwitch cmdlet to add the virtual network adapter named LargeGuid02 as a filter on the Remote Packet Capture provider.

The fifth command removes the virtual network adapter named LargeGuid from the Remote Packet Capture provider.

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
Specifies an array of names of virtual network adapters to remove.

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

[Get-NetEventVmNetworkAdapter](./Get-NetEventVmNetworkAdapter.md)

[Add-NetEventVmNetworkAdapter](./Add-NetEventVmNetworkAdapter.md)

