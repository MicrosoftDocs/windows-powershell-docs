---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NetAdapterPowerManagement.cmdletDefinition.cdxml-help.xml
Module Name: NetAdapter
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/netadapter/set-netadapterpowermanagement?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-NetAdapterPowerManagement
---

# Set-NetAdapterPowerManagement

## SYNOPSIS
Sets the power management properties on the network adapter.

## SYNTAX

### ByName (Default)
```
Set-NetAdapterPowerManagement [-Name] <String[]> [-IncludeHidden] [-ArpOffload <Setting>]
 [-D0PacketCoalescing <Setting>] [-DeviceSleepOnDisconnect <Setting>] [-NSOffload <Setting>]
 [-RsnRekeyOffload <Setting>] [-SelectiveSuspend <Setting>] [-WakeOnMagicPacket <Setting>]
 [-WakeOnPattern <Setting>] [-NoRestart] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByInstanceID
```
Set-NetAdapterPowerManagement -InterfaceDescription <String[]> [-IncludeHidden] [-ArpOffload <Setting>]
 [-D0PacketCoalescing <Setting>] [-DeviceSleepOnDisconnect <Setting>] [-NSOffload <Setting>]
 [-RsnRekeyOffload <Setting>] [-SelectiveSuspend <Setting>] [-WakeOnMagicPacket <Setting>]
 [-WakeOnPattern <Setting>] [-NoRestart] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject (cdxml)
```
Set-NetAdapterPowerManagement -InputObject <CimInstance[]> [-ArpOffload <Setting>]
 [-D0PacketCoalescing <Setting>] [-DeviceSleepOnDisconnect <Setting>] [-NSOffload <Setting>]
 [-RsnRekeyOffload <Setting>] [-SelectiveSuspend <Setting>] [-WakeOnMagicPacket <Setting>]
 [-WakeOnPattern <Setting>] [-NoRestart] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-NetAdapterPowerManagement** cmdlet sets the power management properties on the network adapter.
If only setting the enabled state of the properties, then run the **Enable-NetAdapterPowerManagement** or **Disable-NetAdapterPowerManagement** cmdlet.

## EXAMPLES

### Example 1: Enable device sleep on the disconnect feature on the specified network adapter
```
PS C:\> Set-NetAdapterPowerManagement -Name "Ethernet" -DeviceSleepOnDisconnect Enabled
```

This command enables the device sleep on disconnect feature on the network adapter named Ethernet and restarts the network adapter.

## PARAMETERS

### -ArpOffload
Specifies the address resolution protocol (ARP) offload capability of the network adapter.

The computer, when in low power mode using the ARP offload technology, is able to offload the responsibility of handling responses for incoming ARP protocol requests.

```yaml
Type: Setting
Parameter Sets: (All)
Aliases:
Accepted values: Enabled, Disabled

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AsJob
Runs the cmdlet as a background job.
Use this parameter to run commands that take a long time to complete.
 The cmdlet immediately returns an object that represents the job and then displays the command prompt.
You can continue to work in the session while the job completes.
To manage the job, use the `*-Job` cmdlets.
To get the job results, use the [Receive-Job](https://go.microsoft.com/fwlink/?LinkID=113372) cmdlet.
 For more information about Windows PowerShell® background jobs, see [about_Jobs](https://go.microsoft.com/fwlink/?LinkID=113251).

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
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -D0PacketCoalescing
Specifies the D0 packet coalescing capability of the network adapter.

This feature enables power saving on the computer by reducing the number of receive interrupts.
This reduces the number of receive interrupts by coalescing random broadcast or multi-cast packets.
The processing overhead and power consumption is significantly reduced on the computer.

```yaml
Type: Setting
Parameter Sets: (All)
Aliases:
Accepted values: Enabled, Disabled

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DeviceSleepOnDisconnect
Specifies the device sleep on disconnect capability of the network adapter.

This feature allows the device to stand-by in a low power mode when media is disconnected and wake when media is connected again.

```yaml
Type: Setting
Parameter Sets: (All)
Aliases:
Accepted values: Enabled, Disabled

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IncludeHidden
Indicates that the cmdlet includes both visible and hidden network adapters in the operation.
By default only visible network adapters are included.
If a wildcard character is used in identifying a network adapter and this parameter has been specified, then the wildcard string is matched against both hidden and visible network adapters.

```yaml
Type: SwitchParameter
Parameter Sets: ByName, ByInstanceID
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the input to this cmdlet.
You can use this parameter, or you can pipe the input to this cmdlet.

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

### -InterfaceDescription
Specifies an array of network adapter interface descriptions.
For a physical network adapter this is typically the name of the vendor of the network adapter followed by a part number and description, such as `Contoso 12345 Gigabit Network Device`.

```yaml
Type: String[]
Parameter Sets: ByInstanceID
Aliases: ifDesc, InstanceID

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NSOffload
Specifies the neighbor solicitation (NS) offload capability of the network adapter.

The computer, when in low power mode using the NS offload technology, is able to offload the handling of responses for incoming NS protocol requests.

```yaml
Type: Setting
Parameter Sets: (All)
Aliases:
Accepted values: Enabled, Disabled

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies an array of network adapter names.

```yaml
Type: String[]
Parameter Sets: ByName
Aliases: ifAlias, InterfaceAlias

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NoRestart
Indicates that the cmdlet does not restart the network adapter after completing the operation.
Many advanced properties require restarting the network adapter before the new settings take effect.

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

### -RsnRekeyOffload
Specifies the Wi-Fi robust security network (RSN) rekey offload capability of the network adapter.

The computer, when it goes into sleep state, is able to offload the group temporal key (GTK) rekeying for wake on wireless LAN (WoWLAN).

```yaml
Type: Setting
Parameter Sets: (All)
Aliases:
Accepted values: Enabled, Disabled

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SelectiveSuspend
Specifies the selective suspend capability of the network adapter.

The network drive interface specification (NDIS) selective suspend interface allows NDIS to suspend an idle network adapter by transitioning the adapter to a low-power state.
This enables the computer to reduce the power overhead on the processor and network adapter.

```yaml
Type: Setting
Parameter Sets: (All)
Aliases:
Accepted values: Enabled, Disabled

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

### -WakeOnMagicPacket
Specifies the wake on magic packet capability of the network adapter.

The magic packet is a broadcast frame containing anywhere within its payload 6 bytes of all 255 (FF FF FF FF FF FF in hexadecimal), followed by sixteen repetitions of the 48-bit MAC address of the target computer, for a total of 102 bytes.

```yaml
Type: Setting
Parameter Sets: (All)
Aliases:
Accepted values: Enabled, Disabled

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WakeOnPattern
Manages the wake on pattern capability of the network adapter.

A wake pattern refers to network packet filters that determine if incoming network traffic should wake the computer.
These patterns can be enabled on the network adapter.

The following wake patterns may be supported by a network adapter:
- Wake Pattern.
- Wake on new incoming TCP connection for IPv4 and IPv6 such as TCP SYN IPv4 and TCP SYN IPv6.
- 802.1x re-authentication packets.
- Bitmapped Patterns: Most network adapters can be programmed with bit-mapped pattern filters.
Bitmapped patterns are defined by a bit-map mask and a pattern filter.
As a network packet is received, it is masked using the bitmap mask and then compared to the pattern filter.
If there is a match, then the network adapter wakes the computer.

```yaml
Type: Setting
Parameter Sets: (All)
Aliases:
Accepted values: Enabled, Disabled

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_NetAdapter PowerManagementSettingData[]
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_NetAdapter PowerManagementSettingData
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Disable-NetAdapterPowerManagement](./Disable-NetAdapterPowerManagement.md)

[Enable-NetAdapterPowerManagement](./Enable-NetAdapterPowerManagement.md)

[Get-NetAdapterPowerManagement](./Get-NetAdapterPowerManagement.md)

