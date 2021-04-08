---
author: Kateyanne
external help file: NetAdapter_Cmdlets.xml
manager: dansimp
Module Name: NetAdapter
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/netadapter/set-netadapterpowermanagement?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-NetAdapterPowerManagement

## SYNOPSIS
Sets the power management properties on the network adapter.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-NetAdapterPowerManagement [-Name] <String[]> [-ArpOffload <Setting>] [-AsJob] [-CimSession <CimSession[]>]
 [-D0PacketCoalescing <Setting>] [-DeviceSleepOnDisconnect <Setting>] [-IncludeHidden] [-NoRestart]
 [-NSOffload <Setting>] [-PassThru] [-RsnRekeyOffload <Setting>] [-SelectiveSuspend <Setting>]
 [-ThrottleLimit <Int32>] [-WakeOnMagicPacket <Setting>] [-WakeOnPattern <Setting>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Set-NetAdapterPowerManagement [-ArpOffload <Setting>] [-AsJob] [-CimSession <CimSession[]>]
 [-D0PacketCoalescing <Setting>] [-DeviceSleepOnDisconnect <Setting>] [-NoRestart] [-NSOffload <Setting>]
 [-PassThru] [-RsnRekeyOffload <Setting>] [-SelectiveSuspend <Setting>] [-ThrottleLimit <Int32>]
 [-WakeOnMagicPacket <Setting>] [-WakeOnPattern <Setting>] -InputObject <CimInstance[]> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Set-NetAdapterPowerManagement [-ArpOffload <Setting>] [-AsJob] [-CimSession <CimSession[]>]
 [-D0PacketCoalescing <Setting>] [-DeviceSleepOnDisconnect <Setting>] [-IncludeHidden] [-NoRestart]
 [-NSOffload <Setting>] [-PassThru] [-RsnRekeyOffload <Setting>] [-SelectiveSuspend <Setting>]
 [-ThrottleLimit <Int32>] [-WakeOnMagicPacket <Setting>] [-WakeOnPattern <Setting>]
 -InterfaceDescription <String[]> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Set-NetAdapterPowerManagement** cmdlet sets the power management properties on the network adapter.
If only setting the enabled state of the properties, then run the Enable-NetAdapterPowerManagement or Disable-NetAdapterPowerManagement cmdlet.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Set-NetAdapterPowerManagement -Name Ethernet -DeviceSleepOnDisconnect Enabled
```

This example enables the device sleep on disconnect feature on the network adapter named Ethernet and restarts the network adapter.

## PARAMETERS

### -ArpOffload
Manages the address resolution protocol (ARP) offload capability of the network adapter. 

The computer, when in low power mode using the ARP offload technology, is able to offload the responsibility of handling responses for incoming ARP protocol requests.

```yaml
Type: Setting
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AsJob
ps_cimcommon_asjob

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
Enter a computer name or a session object, such as the output of a New-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -D0PacketCoalescing
Manages the D0 packet coalescing capability of the network adapter. 

This feature enables power saving on the computer by reducing the number of receive interrupts.
This reduces the number of receive interrupts by coalescing random broadcast or multi-cast packets.
The processing overhead and power consumption is significantly reduced on the computer.

```yaml
Type: Setting
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DeviceSleepOnDisconnect
Manages the device sleep on disconnect capability of the network adapter. 

This feature allows the device to stand-by in a low power mode when media is disconnected and wake when media is connected again.

```yaml
Type: Setting
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IncludeHidden
Specifies both visible and hidden network adapters should be included.
By default only visible network adapters are included.
If a wildcard character is used in identifying a network adapter and this parameter has been specified, then the wildcard string is matched against both hidden and visible network adapters.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_3
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
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -InterfaceDescription
Specifies the network adapter interface description.
For a physical network adapter this is typically the name of the vendor of the network adapter followed by a part number and description, such as `Contoso 12345 Gigabit Network Device`.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: ifDesc

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Name
Specifies the name of the network adapter.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: ifAlias, InterfaceAlias

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -NoRestart
Specifies that the network adapter is not restarted as part of running this cmdlet.
Note: Many advanced properties require restarting the network adapter before the new settings take effect.

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

### -NSOffload
Manages the neighbor solicitation (NS) offload capability of the network adapter. 

The computer, when in low power mode using the NS offload technology, is able to offload the handling of responses for incoming NS protocol requests.

```yaml
Type: Setting
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
Manages the Wi-Fi robust security network (RSN) rekey offload capability of the network adapter. 

The computer, when it goes into sleep state, is able to offload the group temporal key (GTK) rekeying for wake on wireless LAN (WoWLAN).

```yaml
Type: Setting
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SelectiveSuspend
Manages the selective suspend capability of the network adapter. 

The network drive interface specification (NDIS) selective suspend interface allows NDIS to suspend an idle network adapter by transitioning the adapter to a low-power state.
This enables the computer to reduce the power overhead on the processor and network adapter.

```yaml
Type: Setting
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

### -WakeOnMagicPacket
Manages the wake on magic packet capability of the network adapter. 

The magic packet is a broadcast frame containing anywhere within its payload `6` bytes of all `255` (`FF FF FF FF FF FF` in hexadecimal), followed by sixteen repetitions of the 48-bit MAC address of the target computer, for a total of `102` bytes.

```yaml
Type: Setting
Parameter Sets: (All)
Aliases: 

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
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

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

