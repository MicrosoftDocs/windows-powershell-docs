---
external help file: NetAdapter_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-anbarr
author: andreabarr
ms.assetid: 34CA425A-4EED-42E9-8614-BBFF6C792393
manager: dansimp
---

# Disable-NetAdapterPowerManagement

## SYNOPSIS
Disables specific power management features on the network adapter.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Disable-NetAdapterPowerManagement [-Name] <String[]> [-ArpOffload] [-AsJob] [-CimSession <CimSession[]>]
 [-D0PacketCoalescing] [-DeviceSleepOnDisconnect] [-IncludeHidden] [-NoRestart] [-NSOffload] [-PassThru]
 [-RsnRekeyOffload] [-SelectiveSuspend] [-ThrottleLimit <Int32>] [-WakeOnMagicPacket] [-WakeOnPattern]
 [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Disable-NetAdapterPowerManagement [-ArpOffload] [-AsJob] [-CimSession <CimSession[]>] [-D0PacketCoalescing]
 [-DeviceSleepOnDisconnect] [-NoRestart] [-NSOffload] [-PassThru] [-RsnRekeyOffload] [-SelectiveSuspend]
 [-ThrottleLimit <Int32>] [-WakeOnMagicPacket] [-WakeOnPattern] -InputObject <CimInstance[]> [-Confirm]
 [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Disable-NetAdapterPowerManagement [-ArpOffload] [-AsJob] [-CimSession <CimSession[]>] [-D0PacketCoalescing]
 [-DeviceSleepOnDisconnect] [-IncludeHidden] [-NoRestart] [-NSOffload] [-PassThru] [-RsnRekeyOffload]
 [-SelectiveSuspend] [-ThrottleLimit <Int32>] [-WakeOnMagicPacket] [-WakeOnPattern]
 -InterfaceDescription <String[]> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Disable-NetAdapterPowerManagement** cmdlet disables specific power management features on the network adapter.
If no power parameters are specified then all power management features are disabled.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Disable-NetAdapterPowerManagement -Name "Ethernet 1"
```

This example disables power management on the network adapter named Ethernet 1 and restarts the network adapter.

### EXAMPLE 2
```
PS C:\>$netAdapter1 = Get-NetAdapter -Name "Ethernet 3"



PS C:\>Disable-NetAdapterPowerManagement -InputObject $netAdapter1


This cmdlet uses the pipeline to select the network adapter named Ethernet 3 and then pipe that object into this cmdlet.
PS C:\>Get-NetAdapter -Name "Ethernet 3" | Disable-NetAdapterPowerManagement
```

This example assigns a variable to the network adapter named Ethernet 3 and then inputs that variable into this cmdlet.

### EXAMPLE 3
```
PS C:\>Disable-NetAdapterManagement -Name "Ethernet 2" -NoRestart
```

This example disables power management on the network adapter named Ethernet 2 and specifies that the network adapter is not restarted.

## PARAMETERS

### -ArpOffload
Manages the address resolution protocol (ARP) offload capability of the adapter. 

The computer, when in low power mode using the ARP offload technology, is able to offload the responsibility of handling responses for incoming ARP protocol requests.

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
This reduces the number of receive interrupts by coalescing random broadcast or multicast packets.
The processing overhead and power consumption is significantly reduced on the computer.

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

### -DeviceSleepOnDisconnect
Manages the device sleep on disconnect capability of the network adapter. 

This feature allows the device to stand-by in a low power mode when media is disconnected and wake when media is connected again.

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
Manages the Wi-Fi robust security network (RSN) rekey offload capability of the network adapter. 

The computer, when it goes into sleep state, is able to offload the group temporal key (GTK) rekeying for wake on wireless LAN (WoWLAN).

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

### -SelectiveSuspend
Manages the selective suspend capability of the network adapter. 

The network drive interface specification (NDIS) selective suspend interface allows NDIS to suspend an idle network adapter by transitioning the adapter to a low-power state.
This enables the computer to reduce the power overhead on the CPU and network adapter.

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

### -WakeOnMagicPacket
Manages the wake on magic packet capability of the network adapter. 

The magic packet is a broadcast frame containing anywhere within its payload `6` bytes of all `255` (`FF FF FF FF FF FF` in hexadecimal), followed by sixteen repetitions of the 48-bit MAC address of the target computer, for a total of `102` bytes.

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

### -WakeOnPattern
Manages the wake on pattern capability of the network adapter. 

A wake pattern refers to network packet filters that determine if incoming network traffic should wake the computer.
These patterns can be enabled on the network adapter. 

The following wake patterns may be supported by a network adapter: 

 - Wake Pattern 

 - Wake on new incoming TCP connection for IPv4 and IPv6 including TCP SYN IPv4 and TCP SYN IPv6. 

 - 802.1x re-authentication packets 

 - Bitmapped Patterns.
Most network adapters can be programmed with bit-mapped pattern filters.
Bitmapped patterns are defined by a bit-map mask and a pattern filter.
As a network packet is received, it is masked using the bitmap mask and then compared to the pattern filter.
If there is a match, then the network adapter wakes the computer.

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

[Enable-NetAdapterPowerManagement](./Enable-NetAdapterPowerManagement.md)

[Get-NetAdapter](./Get-NetAdapter.md)

[Get-NetAdapterPowerManagement](./Get-NetAdapterPowerManagement.md)

[Set-NetAdapterPowerManagement](./Set-NetAdapterPowerManagement.md)

