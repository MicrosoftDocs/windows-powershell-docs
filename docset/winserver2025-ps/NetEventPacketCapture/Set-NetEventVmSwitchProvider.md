---
description: The Set-NetEventVmSwitchProvider cmdlet modifies a virtual machine switch provider for network events.
external help file: MSFT_NetEventVmSwitchProvider.cdxml-help.xml
Module Name: NetEventPacketCapture
ms.date: 10/22/2021
online version: https://learn.microsoft.com/powershell/module/neteventpacketcapture/set-neteventvmswitchprovider?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-NetEventVmSwitchProvider
---

# Set-NetEventVmSwitchProvider

## SYNOPSIS
Modifies a virtual machine switch provider for network events.

## SYNTAX

### BySessionName (Default)
```
Set-NetEventVmSwitchProvider [[-SessionName] <String[]>] [[-Level] <Byte>] [[-MatchAnyKeyword] <UInt64>]
 [[-MatchAllKeyword] <UInt64>] [[-SwitchName] <String>] [[-PortIds] <UInt32[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### BySessionOfTheProvider
```
Set-NetEventVmSwitchProvider [-AssociatedEventSession <CimInstance>] [[-Level] <Byte>]
 [[-MatchAnyKeyword] <UInt64>] [[-MatchAllKeyword] <UInt64>] [[-SwitchName] <String>] [[-PortIds] <UInt32[]>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### InputObject (cdxml)
```
Set-NetEventVmSwitchProvider -InputObject <CimInstance[]> [[-Level] <Byte>] [[-MatchAnyKeyword] <UInt64>]
 [[-MatchAllKeyword] <UInt64>] [[-SwitchName] <String>] [[-PortIds] <UInt32[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-NetEventVmSwitchProvider** cmdlet modifies a virtual machine switch provider for network events.

## EXAMPLES

### Example 1: Add a virtual machine switch provider
```powershell
New-NetEventSession -Name "Session01"
Add-NetEventVMSwitch -Name "Network Adapter 2 - Virtual Switch"
Add-NetEventVmSwitchProvider -SessionName "Session01" -SwitchName "Network Adapter 2 - Virtual Switch"
Set-NetEventVmSwitchProvider -SessionName "Session01" -PortIds 20
```

The first command creates a network event session named `Session01` by using the **New-NetEventSession** cmdlet.

The second command creates a virtual machine switch by using the **Add-NetEventVMSwitch** cmdlet.

The third command creates a virtual machine switch provider for the specified switch.

The fourth command modifies the provider with the specified value.

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
To obtain the network event session, use the **Get-NetEventSession** cmdlet.

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
Specifies the level of Event Tracing for Windows (ETW) events for the provider.
Use the level of detail for the event to filter the events that are logged.
The default value for this parameter is 0x4.
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
Specifies a bitmask that restricts the events that the provider logs.

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
Keywords are flags that you can combine to generate values.
Use a set of hexadecimal values of the keywords instead of the keyword names, and apply a filter to write ETW events for keyword matches.

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

### -PortIds
Specifies port numbers.

```yaml
Type: UInt32[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 3007
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SessionName
Specifies the name of the session that is associated with the **NetEventVMSwitchProvider**.
This parameter has the same value as the **Name** parameter for the **New-NetEventSession** cmdlet.

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

### -SwitchName
Specifies the switch for this virtual machine switch provider.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 3006
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

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

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

### System.String[]

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance[]

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#root/StandardCimv2/MSFT_NetEventVmSwitchProvider

## NOTES

## RELATED LINKS

[Add-NetEventVmSwitchProvider](Add-NetEventVmSwitchProvider.md)

[Get-NetEventVmSwitchProvider](Get-NetEventVmSwitchProvider.md)

[New-NetEventSession](New-NetEventSession.md)

[Remove-NetEventVmSwitchProvider](Remove-NetEventVmSwitchProvider.md)
