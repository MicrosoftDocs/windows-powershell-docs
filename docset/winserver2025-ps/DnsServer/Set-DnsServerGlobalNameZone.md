---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DnsServerGlobalNameZone_v1.0.0.cdxml-help.xml
Module Name: DnsServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dnsserver/set-dnsserverglobalnamezone?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-DnsServerGlobalNameZone
---

# Set-DnsServerGlobalNameZone

## SYNOPSIS
Changes configuration settings for a GlobalNames zone.

## SYNTAX

```
Set-DnsServerGlobalNameZone [-AlwaysQueryServer <Boolean>] [-BlockUpdates <Boolean>] [-Enable <Boolean>]
 [-EnableEDnsProbes <Boolean>] [-GlobalOverLocal <Boolean>] [-PreferAaaa <Boolean>] [-ComputerName <String>]
 [-SendTimeout <UInt32>] [-ServerQueryInterval <TimeSpan>] [-PassThru] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-DnsServerGlobalNameZone** cmdlet enables or disables single-label Domain Name System (DNS) queries.
It also changes configuration settings for a GlobalNames zone.

The GlobalNames zone supports short, easy-to-use names instead of fully qualified domain names (FQDNs) without using Windows Internet Name Service (WINS) technology.
For instance, DNS can query SarahJonesDesktop instead of SarahJonesDesktop.contoso.com.

## EXAMPLES

### Example 1: Enable a GlobalNames zone
```
PS C:\> Set-DnsServerGlobalNameZone -Enable $True -PassThru
```

This command enables a GlobalNames zone on the current server.

## PARAMETERS

### -AlwaysQueryServer
Specifies whether a DNS server attempts to use cache values to update a list of DNS servers.
This value has no effect if the DNS server hosts a GlobalNames zone.

If the value is $True, a DNS server queries a remote DNS server for an update to the list of remote DNS servers that are hosting a GlobalNames zone.

If the value is $False, a DNS server attempts to use cached local service records for a GlobalNames zone to get an update to the list.

The default value is $False.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

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

### -BlockUpdates
Specifies whether a DNS server blocks updates in authoritative zones for FQDNs that conflict with labels in a GlobalNames zone.
If the value is $True, a DNS server checks for a conflict and blocks an update when it finds a conflict.
If the value is $False, the server does not check.
The default value is $True.

To check for conflicts, the DNS server removes the zone name (rightmost labels) and performs a search that is not case sensitive on its locally hosted GlobalNames zone.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Specifies a DNS server.
If you do not specify this parameter, the command runs on the local system.
You can specify an IP address or any value that resolves to an IP address, such as a fully qualified domain name (FQDN), host name, or NETBIOS name.

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

### -Enable
Specifies whether to use a GlobalNames zone to resolve single-label names.
A value of $True enables the use of GlobalNames.
A value of $False disables the use of GlobalNames.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EnableEDnsProbes
Specifies whether a DNS server honors the EnableEDnsProbes value for a remote GlobalNames zone.
A DNS server can allow or refuse queries on Extended DNS (EDNS) information.

If this value is $True, the server attempts EDNS queries for remote GlobalNames zones if the zones permit.

If this value is $False, a DNS server does not attempt ENDS queries for remote GlobalNames zones.

The default value is $False.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -GlobalOverLocal
Specifies whether a DNS server first attempts to resolve names through a query of zones for which it is authoritative.
If the value is $True, a DNS server queries locally and then queries the GlobalNames zone.
If the value is $False, the server queries the GlobalNames zone and then queries globally.
The default value is $False.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

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

### -PreferAaaa
Specifies whether a DNS server prefers IPv6 (AAAA) address records over IPv4 (A) address records for queries to a remote DNS server that hosts a GlobalNames zone.

If this value is $True, a DNS server uses IPv6 addresses, unless no IPv6 value is available.

If this value is $False, a DNS server uses IPv4 addresses, unless no IPv4 value is available.

The default value is $False.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SendTimeout
Specifies the number of seconds that a DNS server waits for a response to a query to a remote GlobalNames zone.

The minimum value is 1.
The maximum value is 15.

The default value is 3.
A DNS server interprets a value of 0 as the default value, 3.

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

### -ServerQueryInterval
Specifies an interval, as a time-span object, between queries to refresh the set of remote DNS servers that are hosting the GlobalNames zone.

The minimum value is 60 seconds.
The maximum value is 30 days.

The default value is six hours.
A DNS server interprets a value of 0 as the default value, six hours.

```yaml
Type: TimeSpan
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

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#DnsServerGlobalNameZone

## NOTES

## RELATED LINKS

