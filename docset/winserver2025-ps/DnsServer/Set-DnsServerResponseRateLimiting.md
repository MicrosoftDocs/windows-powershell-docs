---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DnsServerResponseRateLimiting_v1.0.0.cdxml-help.xml
Module Name: DnsServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dnsserver/set-dnsserverresponseratelimiting?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-DnsServerResponseRateLimiting
---

# Set-DnsServerResponseRateLimiting

## SYNOPSIS
Enables RRL on a DNS server.

## SYNTAX

```
Set-DnsServerResponseRateLimiting [-ResponsesPerSec <UInt32>] [-ErrorsPerSec <UInt32>] [-WindowInSec <UInt32>]
 [-IPv4PrefixLength <UInt32>] [-IPv6PrefixLength <UInt32>] [-LeakRate <UInt32>] [-ResetToDefault]
 [-TruncateRate <UInt32>] [-MaximumResponsesPerWindow <UInt32>] [-Mode <String>] [-ComputerName <String>]
 [-PassThru] [-Force] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-DnsServerResponseRateLimiting** cmdlet enables Response Rate Limiting (RRL) on a Windows DNS server.

## EXAMPLES

### Example 1: Set RRL parameters on a DNS server
```
PS C:\> Set-DnsServerResponseRateLimiting -WindowInSec 7 -LeakRate 4 -TruncateRate 3 -ErrorsPerSec 8 -ResponsesPerSec 8
```

This command sets the RRL parameters on the DNS Server.

### Example 2: Reset RRL settings to default values
```
PS C:\> Set-DnsServerResponseRateLimiting -ResetToDefault
```

This command resets all the RRL parameters on the DNS Server to default values.

### Example 3: Set RRL to LogOnly mode
```
PS C:\> Set-DnsServerRRL -Mode LogOnly
```

This command sets the RRL on the DNS server to **LogOnly** mode.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

The cmdlet immediately returns an object that represents the job and then displays the command prompt.
You can continue to work in the session while the job completes.
To manage the job, use the `*-Job` cmdlets.
To get the job results, use the [Receive-Job](https://go.microsoft.com/fwlink/?LinkID=113372) cmdlet.

For more information about Windows PowerShell background jobs, see [about_Jobs](https://go.microsoft.com/fwlink/?LinkID=113251).

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

### -ComputerName
Specifies a remote DNS server.
You can specify an IP address or any value that resolves to an IP address, such as a fully qualified domain name (FQDN), host name, or NetBIOS name.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Cn

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

### -ErrorsPerSec
Specifies the maximum number of times that the server can send an error response to a client within a one-second interval.
The error responses include: REFUSED, FORMERR and SERVFAIL

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Force
Forces the command to run without asking for user confirmation.

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

### -IPv4PrefixLength
Specifies the IPv4 prefix length, which indicates the size of the subnet in which the incoming queries are grouped.
The server applies RRL if queries resulting in the same response occur more frequently than expected in a specified time window.
The default value of this parameter is 24.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IPv6PrefixLength
Specifies the IPv6 prefix length, which indicates the size of the IPv6 subnet in which the incoming queries are grouped.
The server applies RRL if queries resulting in the same response occur more frequently than expected in a specified time window.
The default value of this parameter is 56.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LeakRate
Specifies the rate at which the server responds to dropped queries.
For queries that meet criteria to be dropped due to RRL, the DNS server still responds once per *LeakRate* queries.
For example, if *LeakRate* is 3, the server responds to one in every 3 queries.
The allowed range for LeakRate is 2 to 10.
If *LeakRate* is set to zero, then no responses are 'leaked' by RRL.
*LeakRate* leaves a chance for the victims in the same subnet as the forged IP address to get responses to their valid queries.
The default value for *LeakRate* is 3.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MaximumResponsesPerWindow


```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Mode
Specifies the state of RRL on the DNS server.
The acceptable values for this parameter are: Enable, or Disable, or LogOnly.
If the mode is set to LogOnly the DNS server performs all the RRL calculations but instead of taking the preventive actions (dropping or truncating responses), it only logs the potential actions as if RRL were enabled and continues with the normal responses.
The default value is Enable.

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: LogOnly, Enable, Disable

Required: False
Position: Named
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

### -ResetToDefault
Indicates that this cmdlet sets all the RRL settings to their default values.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResponsesPerSec
Specifies the maximum number of times that the server sends a client the same response within a one-second interval.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -TruncateRate
Specifies the rate at which the server responds with truncated responses.
For queries that meet the criteria to be dropped due to RRL, the DNS server still responds with truncated responses once per *TruncateRate* queries.
For example, if *TruncateRate* is 2, one in every 2 queries receives a truncated response.
The *TruncateRate* parameter provides the valid clients a way to reconnect using TCP.
The allowed range for TruncateRate is 2 to 10.
If it is set to 0, then this behaviour is disabled.
The default value is 2.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -WindowInSec
Specifies the period (in seconds) over which rates are measured and averaged for RRL.
RRL is applied if queries from same subnet, resulting in same response, occur more frequently than expected in a specified time window.
The default value is 5.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#DnsServerResponseRateLimiting
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Add-DnsServerResponseRateLimitingExceptionlist](./Add-DnsServerResponseRateLimitingExceptionlist.md)

[Get-DnsServerResponseRateLimiting](./Get-DnsServerResponseRateLimiting.md)

[Set-DnsServerResponseRateLimitingExceptionlist](./Set-DnsServerResponseRateLimitingExceptionlist.md)

