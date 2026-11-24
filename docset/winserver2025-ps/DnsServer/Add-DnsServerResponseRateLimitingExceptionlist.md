---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DnsServerResponseRateLimitingExceptionlist_v1.0.0.cdxml-help.xml
Module Name: DnsServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dnsserver/add-dnsserverresponseratelimitingexceptionlist?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-DnsServerResponseRateLimitingExceptionlist
---

# Add-DnsServerResponseRateLimitingExceptionlist

## SYNOPSIS
Adds an RRL exception list on the DNS server.

## SYNTAX

```
Add-DnsServerResponseRateLimitingExceptionlist [[-ClientSubnet] <String>] [[-Fqdn] <String>]
 [[-ServerInterfaceIP] <String>] [[-Name] <String>] [[-Condition] <String>] [-PassThru]
 [-ComputerName <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Add-DnsServerResponseRateLimiting** cmdlet adds a Response Rate Limiting (RRL) exception list on the DNS server.
The RRL exception list indicates that responses to queries for specified Fully Qualified Domain Names (FQDNs), queries originating from specified client subnets, queries received on specified server interfaces, or any combination of these values, are exempt from RRL.

## EXAMPLES

### Example 1: Add a domain to an RRL exception list
```
PS C:\> Add-DnsServerResponseRateLimitingExceptionlist -Name "SafeList1" -Fqdn "EQ,*.contoso.com"
```

This command adds an RRL exception for the domain contoso.com.

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

### -ClientSubnet
Specifies the client subnet values for the exception list.

This parameter must have the following format: `COMPARATOR, value1, value2,..., COMPARATOR, value 3, value 4,..` where the COMPARATOR can be EQ or NE.
There can be only one EQ and one NE in a value.

The values following the EQ operator will be treated as multiple assertions which are logically combined using the OR operator.
The values following the NE operator will be treated as multiple assertions which are logically differenced using the AND operator.

Multiple values are combined using the *Condition* parameter as a logical operator.
The same operator is also used for combining EQ and NE expressions within a value.

For example, `EQ, America, Asia, NE, Europe` specifies that the client subnets of America and Asia are in the exception list, and the client subnet of Europe is not.

For details, see **Add-DnsServerClientSubnet**.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ComputerName
Specifies a remote DNS server on which to run the command.
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

### -Condition
Specifies a logical operator for combining multiple values of the **ClientSubnet**, **Fqdn** and **ServerIp** parameters.
The values for the parameters are combined using the *Condition* parameter as a logical operator.
The same operator is also used for combining EQ and NE expressions within a value.
The default value is AND.

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: AND, OR

Required: False
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -Fqdn
Specifies FQDN values for the exception list.

The value must have the following format: `COMPARATOR, value1, value2,..., COMPARATOR, value 3, value 4,..` where the COMPARATOR can be EQ or NE.
There can be only one EQ and one NE in a value.

The values following the EQ operator will be treated as multiple assertions which are logically combined using the OR operator.
The values following the NE operator will be treated as multiple assertions which are logically differenced using the AND operator.

Multiple values are combined using the *Condition* parameter as a logical operator.
The same operator is also used for combining EQ and NE expressions within a value.

For example, `EQ,*.contoso.com` specifies that the contoso.com domain should be added to the exception list.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of the RRL exception list.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
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

### -ServerInterfaceIP
Specifies the server interface on which the DNS server is listening.

The value must have the following format: `COMPARATOR, value1, value2,..., COMPARATOR, value 3, value 4,..` where the COMPARATOR can be EQ or NE.
There can be only one EQ and one NE in a value.

The values following the EQ operator are treated as multiple assertions which are logically combined using the OR operator.
The values following the NE operator are treated as multiple assertions which are logically differenced using the AND operator.

Multiple values are combined using the *Condition* parameter as a logical operator.
The same operator is also used for combining EQ and NE expressions within a value.

For example, `EQ,10.0.0.3` specifies that all queries received on a server interface that has the IP address of 10.0.0.3 should be exempt from RRL.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 4
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

### Microsoft.Management.Infrastructure.CimInstance#DnsServerResponseRateLimitingExceptionlist
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Add-DnsServerClientSubnet](./Add-DnsServerClientSubnet.md)

[Get-DnsServerResponseRateLimitingExceptionlist](./Get-DnsServerResponseRateLimitingExceptionlist.md)

[Set-DnsServerResponseRateLimiting](./Set-DnsServerResponseRateLimiting.md)

[Set-DnsServerResponseRateLimitingExceptionlist](./Set-DnsServerResponseRateLimitingExceptionlist.md)

