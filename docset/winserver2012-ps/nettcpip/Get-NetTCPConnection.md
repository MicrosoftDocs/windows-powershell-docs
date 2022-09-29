---
external help file: NetTCPIP_Cmdlets.xml
Module Name: NetTCPIP
online version: https://learn.microsoft.com/powershell/module/nettcpip/get-nettcpconnection?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-NetTCPConnection

## SYNOPSIS
Gets information about current TCP connection statistics.

## SYNTAX

```
Get-NetTCPConnection [[-LocalAddress] <String[]>] [[-LocalPort] <UInt16[]>]
 [-AppliedSetting <AppliedSetting[]>] [-AsJob] [-CimSession <CimSession[]>] [-RemoteAddress <String[]>]
 [-RemotePort <UInt16[]>] [-State <State[]>] [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Get-NetTCPConnection** cmdlet gets information about current TCP connection statistics.
This includes TCP connection properties such as local or remote IP address, local or remote port and connection state.
Used without parameters, this cmdlet gets information about all TCP connections.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-NetTCPConnection
```

This example gets information about current TCP connection statistics.
Used without parameters, this cmdlet gets information about all TCP connections.

### EXAMPLE 2
```
PS C:\>Get-NetTCPConnection -State Established
```

This example gets information about all established TCP connections.

### EXAMPLE 3
```
PS C:\>Get-NetTCPConnection -AppliedSetting Internet
```

This example gets information about all TCP connections that use the Internet TCP settings.

## PARAMETERS

### -AppliedSetting
Gets TCP connection information only about a specific AppliedSetting.
The TCP settings defined in NetTCPSetting are applied to each TCP connection associated with a transport filter.
The acceptable values for this parameter are:

 -- Internet: The TCP connections that use Internet TCP settings. 

 -- Datacenter: The TCP connections that use data center TCP settings. 

 -- Compat: The TCP connections that use compatibility TCP settings. 

 -- Custom: The TCP connections that use custom TCP settings.

```yaml
Type: AppliedSetting[]
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

### -LocalAddress
Gets TCP connection information only about connections from a specific local IP address.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LocalPort
Gets TCP connection information only about connections from a specific local TCP port.

```yaml
Type: UInt16[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoteAddress
Gets TCP connection information only about connections from a specific remote IP address.

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

### -RemotePort
Gets TCP connection information only about connections from a specific remote TCP port.

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

### -State
Gets TCP connection information only about connections in a specific TCP state.
Transmission Control Protocol (TCP) and the TCP state machine are described in RFC 793http://tools.ietf.org/html/rfc793.

```yaml
Type: State[]
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

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_NetTCPConnection
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS
