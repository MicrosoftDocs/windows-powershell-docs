---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DnsServerRecursion_v1.0.0.cdxml-help.xml
Module Name: DnsServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dnsserver/set-dnsserverrecursion?view=windowsserver2019-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-DnsServerRecursion
---

# Set-DnsServerRecursion

## SYNOPSIS
Modifies recursion settings for a DNS server.

## SYNTAX

```
Set-DnsServerRecursion [-ComputerName <String>] [-AdditionalTimeout <UInt32>] [-RetryInterval <UInt32>]
 [-Timeout <UInt32>] [-Enable <Boolean>] [-PassThru] [-SecureResponse <Boolean>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-DnsServerRecursion** cmdlet modifies recursion settings for a Domain Name System (DNS) server.
Recursion occurs when a DNS server queries other DNS servers on behalf of a requesting client, and then sends the answer back to the client.

## EXAMPLES

### Example 1: Set the retry interval
```
PS C:\> Set-DnsServerRecursion -RetryInterval 3 -PassThru

Enable               : False
AdditionalTimeout(s) : 4
RetryInterval(s)     : 15
Timeout(s)           : 8
SecureResponse       : True
```

This command sets the retry interval to 3 seconds.

## PARAMETERS

### -AdditionalTimeout
Specifies the time interval, in seconds, that a DNS server waits as it uses recursion to get resource records from a remote DNS server.
We recommend that you limit the value to the range 0x00000000 to 0x0000000F (0 seconds to 15 seconds), inclusive.
However, you can use any value.
We recommend that you set the default value to 4.

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
Specifies a DNS server.
The acceptable values for this parameter are: an IPv4 address; an IPv6 address; and any other value that resolves to an IP address, such as a fully qualified domain name (FQDN), host name, or NETBIOS name.

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
Specifies whether the server enables recursion.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: EnableRecursion

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

### -RetryInterval
Specifies elapsed seconds before a DNS server retries a recursive lookup.
If the parameter is undefined or zero, the DNS server retries after three seconds.
Valid values are in the range of 1 second to 15 seconds.

We recommend that in general, you do not change the value of this parameter.
However, under a few circumstances you should consider changing the parameter value.
For example, if a DNS server contacts a remote DNS server over a slow link and retries the lookup before it gets a response, you can raise the retry interval to be slightly longer than the observed response time.

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

### -SecureResponse
Indicates whether a DNS server screens DNS records against the zone of authority for the remote server, to prevent cache pollution.
If you set this to $True, the DNS server caches only those records that are in the zone of authority for the queried remote server.
Otherwise, the server caches all records in the remote server cache.

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

### -Timeout
Specifies the number of seconds that a DNS server waits before it stops trying to contact a remote server.
The valid value is in the range of 0x1 to 0xFFFFFFFF (1 second to 15 seconds).
The default setting is 0x8 (8 seconds).
We recommend that you increase this value when recursion occurs over a slow link.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#DnsServerRecursion

## NOTES

## RELATED LINKS

[Get-DnsServerRecursion](./Get-DnsServerRecursion.md)

