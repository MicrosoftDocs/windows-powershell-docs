---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DnsServerForwarder_v1.0.0.cdxml-help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Set-DnsServerForwarder
ms.reviewer:
ms.assetid: 84E01CE5-F695-4982-8131-F21FC8ACCD7F
---

# Set-DnsServerForwarder

## SYNOPSIS
Changes forwarder settings on a DNS server.

## SYNTAX

```
Set-DnsServerForwarder [[-IPAddress] <IPAddress[]>] [-ComputerName <String>] [-UseRootHint <Boolean>]
 [-Timeout <UInt32>] [-EnableReordering <Boolean>] [-PassThru] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-DnsServerForwarder** cmdlet changes forwarder settings on a Domain Name System (DNS) server.
This cmdlet sets or resets IP addresses to which the DNS server forwards DNS queries when it cannot solve them locally.
This cmdlet overwrites existing server level forwarders.

Setting IP addresses by using this cmdlet causes the DNS server to perform recursive queries to the DNS servers at the specified IP addresses.
By default, the DNS server waits five seconds for a response from one forwarder IP address before it tries another forwarder IP address.
You can use the *Timeout* parameter to change the number of seconds that the DNS server waits.
When the server has exhausted all forwarders, it attempts standard recursion.
By default, a DNS server performs iterative queries when it cannot resolve a query.

## EXAMPLES

### Example 1: Set a forwarder on a DNS server
```
PS C:\> Set-DnsServerForwarder -IPAddress "10.0.0.1" -PassThru
```

This command overwrites the list of existing forwarders on a DNS server and specifies the IP address of a DNS server where queries are forwarded.

### Example 2: Disable reordering of forwarders on a DNS server
```
PS C:\> Set-DnsServerForwarder -EnableReordering $False -PassThru
```

This command disables dynamic reordering of forwarders on a DNS server.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete. 

The cmdlet immediately returns an object that represents the job and then displays the command prompt. 
You can continue to work in the session while the job completes. 
To manage the job, use the `*-Job` cmdlets. 
To get the job results, use the [Receive-Job](http://go.microsoft.com/fwlink/?LinkID=113372) cmdlet. 

For more information about Windows PowerShell background jobs, see [about_Jobs](http://go.microsoft.com/fwlink/?LinkID=113251).

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
Enter a computer name or a session object, such as the output of a [New-CimSession](http://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](http://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
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

### -EnableReordering
Specifies whether to enable the DNS server to reorder forwarders dynamically.

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

### -IPAddress
Specifies an array of IP addresses of DNS servers where queries are forwarded.
Specify the forwarders in the order that you want them to be configured.

```yaml
Type: IPAddress[]
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
Specifies the number of seconds that the DNS server waits for a response from the forwarder.
The minimum value is 0, and the maximum value is 15.
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

### -UseRootHint
Specifies whether to prevent the DNS server from performing iterative queries.
If you set **UseRootHint** to $false, the DNS server forwards unresolved queries only to the DNS servers in the forwarders list and does not try iterative queries if the forwarders do not resolve the queries.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

###  
Class DNSForwarderSettings

{

uint32  ForwardDelegations; // Specifies whether the DNS server forwards queries to delegated subzones.

DNSForwarders  Forwarders\[\]; //Enumerates the list of IP addresses of forwarders to which the DNS server forwards queries.

uint32  ForwardingTimeout; // Time, in seconds, that a DNS server that is forwarding a query will wait for resolution from the forwarder before it attempts to resolve the query itself.
This value is meaningless if the forwarding server is not set to use recursion.
To determine this, check the **IsSlave** Boolean property.

boolean IsSlave; //True if the DNS server does not use recursion when name resolution through forwarders fails.

}

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#DnsServerForwarder

## NOTES

## RELATED LINKS

[Get-DnsServerForwarder](./Get-DnsServerForwarder.md)

[Add-DnsServerForwarder](./Add-DnsServerForwarder.md)

[Remove-DnsServerForwarder](./Remove-DnsServerForwarder.md)

