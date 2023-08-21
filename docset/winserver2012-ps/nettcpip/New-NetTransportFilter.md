---
external help file: NetTCPIP_Cmdlets.xml
Module Name: NetTCPIP
online version: https://learn.microsoft.com/powershell/module/nettcpip/new-nettransportfilter?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# New-NetTransportFilter

## SYNOPSIS
Creates a transport filters.

## SYNTAX

```
New-NetTransportFilter [-AsJob] [-CimSession <CimSession[]>] [-DestinationPrefix <String>]
 [-LocalPortEnd <UInt16>] [-LocalPortStart <UInt16>] [-Protocol <Protocol>] [-RemotePortEnd <UInt16>]
 [-RemotePortStart <UInt16>] [-ThrottleLimit <Int32>] -SettingName <String> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **New-NetTransportFilter** cmdlet creates a transport filter.
A transport filter determines how TCP settings from NetTcpSetting are applied to an IP address prefix or a TCP port range.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>New-NetTransportFilter -SettingName Datacenter -DestinationPrefix 192.168.0.0/16
```

This example creates a transport filter for the 192.168.0.0/16 network.
The data center TCP settings will apply to all TCP connections that are between the computer and other computers in this network.

### EXAMPLE 2
```
PS C:\>Get-NetTransportFilter -SettingName Compat -LocalPortStart 5000 -LocalPortEnd 5000 -RemotePortStart 6000 -RemotePortEnd 6000
```

This example creates a transport filter for an app that needs conservative TCP settings to ensure compatibility.

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
Creates transport filter by DestinationPrefix.
The DestinationPrefix determines if a transport filter is applied to TCP connections to addresses in that range.
The DestinationPrefix includes a destination network identifier and a prefix length, separated by a slash (/).

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LocalPortEnd
Creates a transport filter by local TCP port.
The LocalPortEnd determines if a transport filter is applied to TCP connections based on the local port number that sets the upper bound of a range.

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LocalPortStart
Creates a transport filter by local TCP port.
The LocalPortEnd determines if a transport filter is applied to TCP connections based on the local port number that sets the lower bound of a range.

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Protocol
Represents a read-only setting set to TCP.

```yaml
Type: Protocol
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemotePortEnd
Creates a transport filter by remote TCP port.
The RemotePortEnd determines if a transport filter is applied to TCP connections based on the remote port number that sets the upper bound of a range.

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemotePortStart
Creates a transport filter by remote TCP port.
The RemotePortStart determines if a transport filter is applied to TCP connections based on the remote port number that sets the lower bound of a range.

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SettingName
Associates a transport filter with a specific SettingName.
The TCP settings defined in NetTCPSetting are applied to each TCP connection associated with a transport filter.
The acceptable values for this parameter are:

 -- Internet: The transport filters that apply Internet TCP settings. 

 -- Datacenter: The transport filters that apply data center TCP settings. 

 -- Compat: The transport filters that apply compatibility TCP settings. 

 -- Custom: The transport filters that apply custom TCP settings.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
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

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_NetTransportFilter
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Get-NetTransportFilter](./Get-NetTransportFilter.md)

[Remove-NetTransportFilter](./Remove-NetTransportFilter.md)

[Set-NetTCPSetting](./Set-NetTCPSetting.md)

