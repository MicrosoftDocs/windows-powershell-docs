---
external help file: NetTCPIP_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-anbarr
author: andreabarr
ms.assetid: 54CBC60C-5295-4FCC-8F7C-2FC73E26DACC
manager: dansimp
---

# Remove-NetTransportFilter

## SYNOPSIS
Deletes a transport filter.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Remove-NetTransportFilter [-AsJob] [-AssociatedTCPSetting <CimInstance>] [-CimSession <CimSession[]>]
 [-DestinationPrefix <String[]>] [-LocalPortEnd <UInt16[]>] [-LocalPortStart <UInt16[]>] [-PassThru]
 [-Protocol <Protocol[]>] [-RemotePortEnd <UInt16[]>] [-RemotePortStart <UInt16[]>] [-SettingName <String[]>]
 [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Remove-NetTransportFilter [-AsJob] [-CimSession <CimSession[]>] [-PassThru] [-ThrottleLimit <Int32>]
 -InputObject <CimInstance[]> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Remove-NetTransportFilter** cmdlet deletes a transport filter.
A transport filter determines how TCP settings from NetTcpSetting are applied to an IP address prefix or a TCP port range.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Remove-NetTransportFilter -SettingName Custom
```

This example removes all of the transport filters on the server that are associated with the custom NetTcpSetting.

### EXAMPLE 2
```
PS C:\>Get-NetTCPSetting -InitialCongestionWindowMss 4 | Remove-NetTransportFilter
```

This example gets all of the NetTcpSettings that have an initial congestion window of 4 MSS and removes their associated transport filters.

## PARAMETERS

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

### -AssociatedTCPSetting
Removes all of the transport filters that are associated with a specific network TCP setting CIM object.
This is typically as input through a pipeline.

```yaml
Type: CimInstance
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### -DestinationPrefix
Deletes transport filters by destination prefix.
This parameter value determines if a transport filter is applied to TCP connections to addresses in that range.
This parameter value includes a destination network identifier and a prefix length, separated by a slash (/).

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
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

### -LocalPortEnd
Deletes transport filters by local TCP port.
The LocalPortEnd determines if a transport filter is applied to TCP connections based on the local port number that sets the upper bound of a range.

```yaml
Type: UInt16[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LocalPortStart
Deletes transport filters by local TCP port.
This parameter value determines if a transport filter is applied to TCP connections based on the local port number that sets the lower bound of a range.

```yaml
Type: UInt16[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
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

### -Protocol
Specifies a read-only setting set to TCP.

```yaml
Type: Protocol[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemotePortEnd
Deletes transport filters by remote TCP port.
This parameter value determines if a transport filter is applied to TCP connections based on the remote port number that sets the upper bound of a range.

```yaml
Type: UInt16[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemotePortStart
Deletes transport filters by remote TCP port.
This parameter value determines if a transport filter is applied to TCP connections based on the remote port number that sets the lower bound of a range.

```yaml
Type: UInt16[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SettingName
Deletes transport filters by setting name.
The TCP settings defined in NetTCPSetting are applied to each TCP connection associated with a transport filter.
The acceptable values for this parameter are:

 -- Compat: The transport filters that apply compatibility TCP settings. 

 -- Custom: The transport filters that apply custom TCP settings. 

 -- Datacenter: The transport filters that apply data center TCP settings. 

 -- Internet: The transport filters that apply Internet TCP settings.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
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

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_NetTransportFilter
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Get-NetTCPSetting](./Get-NetTCPSetting.md)

[Get-NetTransportFilter](./Get-NetTransportFilter.md)

[New-NetTransportFilter](./New-NetTransportFilter.md)

