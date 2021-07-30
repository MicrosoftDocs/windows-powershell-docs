---
external help file: NetTCPIP_Cmdlets.xml
Module Name: NetTCPIP
online version: https://docs.microsoft.com/powershell/module/nettcpip/get-nettransportfilter?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-NetTransportFilter

## SYNOPSIS
Gets information about transport filters.

## SYNTAX

```
Get-NetTransportFilter [-AsJob] [-AssociatedTCPSetting <CimInstance>] [-CimSession <CimSession[]>]
 [-DestinationPrefix <String[]>] [-LocalPortEnd <UInt16[]>] [-LocalPortStart <UInt16[]>]
 [-Protocol <Protocol[]>] [-RemotePortEnd <UInt16[]>] [-RemotePortStart <UInt16[]>] [-SettingName <String[]>]
 [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Get-NetTransportFilter** cmdlet gets information about transport filters.
A transport filter determines how TCP settings from NetTcpSetting are applied to an IP address prefix or a TCP port range.

Without parameters, this cmdlet returns all transport filters on the computer.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-NetTransportFilter
```

This example gets information about transport filters.
Without parameters, this cmdlet returns all transport filters on the computer.

### EXAMPLE 2
```
PS C:\>Get-NetTransportFilter -SettingName Internet
```

This example gets information about the transport filters that apply Internet settings.

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
Gets transport filter information that applies to a specific network TCP setting CIM object.
This is typically as input through the pipeline.

```yaml
Type: CimInstance
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a New-CimSessionhttps://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttps://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
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
Gets transport filter information only about a specific DestinationPrefix.
The DestinationPrefix determines if a transport filter is applied to TCP connections to addresses in that range.
The DestinationPrefix includes a destination network identifier and a prefix length, separated by a slash (/).

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LocalPortEnd
Gets transport filter information only about a specific LocalPortEnd.
The LocalPortEnd determines if a transport filter is applied to TCP connections based on the local port number that sets the upper bound of a range.

```yaml
Type: UInt16[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LocalPortStart
Gets transport filter information only about a specific LocalPortStart.
The LocalPortStart determines if a transport filter is applied to TCP connections based on the local port number that sets the lower bound of a range.

```yaml
Type: UInt16[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Protocol
Gets transport filter based on protocol.
Protocol is a read-only setting set to TCP.

```yaml
Type: Protocol[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemotePortEnd
Gets transport filter information only about a specific RemotePortEnd.
The RemotePortEnd determines if a transport filter is applied to TCP connections based on the remote port number that sets the upper bound of a range.

```yaml
Type: UInt16[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemotePortStart
Gets transport filter information only about a specific RemotePortStart.
The RemotePortStart determines if a transport filter is applied to TCP connections based on the remote port number that sets the lower bound of a range.

```yaml
Type: UInt16[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SettingName
Gets transport filter information only about a specific SettingName.
The TCP settings defined in NetTCPSetting are applied to each TCP connection associated with a transport filter.
The acceptable values for this parameter are:

 -- Internet: The transport filters that apply Internet TCP settings. 

 -- Datacenter: The transport filters that apply data center TCP settings. 

 -- Compat: The transport filters that apply compatibility TCP settings. 

 -- Custom: The transport filters that apply custom TCP settings.

```yaml
Type: String[]
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

## INPUTS

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_NetTransportFilter
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Get-NetUDPSetting](./Get-NetUDPSetting.md)

[New-NetTransportFilter](./New-NetTransportFilter.md)

[Remove-NetTransportFilter](./Remove-NetTransportFilter.md)

[Set-NetTCPSetting](./Set-NetTCPSetting.md)

[Set-NetUDPSetting](./Set-NetUDPSetting.md)

