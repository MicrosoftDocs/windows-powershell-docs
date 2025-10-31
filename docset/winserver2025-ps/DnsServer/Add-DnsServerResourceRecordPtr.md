---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DnsServerResourceRecordPTR_v1.0.0.cdxml-help.xml
Module Name: DnsServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dnsserver/add-dnsserverresourcerecordptr?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-DnsServerResourceRecordPtr
---

# Add-DnsServerResourceRecordPtr

## SYNOPSIS
Adds a type PTR resource record to a DNS server.

## SYNTAX

```
Add-DnsServerResourceRecordPtr [-AllowUpdateAny] [-PtrDomainName] <String> [-Name] <String>
 [-ComputerName <String>] [-ZoneName] <String> [-TimeToLive <TimeSpan>] [-AgeRecord] [-PassThru]
 [-ZoneScope <String>] [-VirtualizationInstance <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-DnsServerResourceRecordPtr** cmdlet adds a specified pointer (PTR) record to a specified Domain Name System (DNS) zone.

PTR resource records support reverse lookup based on the in-addr.arpa domain.
PTR records locate a computer by its IP address and resolve the address to the DNS domain name for that computer.

## EXAMPLES

### Example 1: Add a PTR record
```
PS C:\> Add-DnsServerResourceRecordPtr -Name "17" -ZoneName "0.168.192.in-addr.arpa" -AllowUpdateAny -TimeToLive 01:00:00 -AgeRecord -PtrDomainName "host17.contoso.com"
```

This command adds a type PTR DNS record in the zone named contoso.com.
The record maps IP address 192.168.0.17 to the name host17.contoso.com.
The command includes the **AllowUpdateAny** and **AgeRecord** parameters, and provides a TTL value.
Because the command includes the *AgeRecord* parameter, a DNS server can scavenge this record.

## PARAMETERS

### -AgeRecord
Indicates that the DNS server uses a time stamp for the resource record that this cmdlet adds.
A DNS server can scavenge resource records that have become stale based on a time stamp.

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

### -AllowUpdateAny
Indicates that any authenticated user can update a resource record that has the same owner name.

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

### -Name
Specifies part of the IP address for the host.
You can use either an IPv4 or IPv6 address.
For example, if you use an IPv4 class C reverse lookup zone, then **Name** specifies the last octet of the IP address.
If you use a class B reverse lookup zone, then **Name** specifies the last two octets.

```yaml
Type: String
Parameter Sets: (All)
Aliases: RecordName

Required: True
Position: 2
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

### -PtrDomainName
Specifies an FQDN for a resource record in the DNS namespace.
This value is the response to a reverse lookup using this PTR.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 3
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

### -TimeToLive
Specifies the Time to Live (TTL) value, in seconds, for a resource record.
Other DNS servers use this length of time to determine how long to cache a record.

The Start of Authority (SOA) record defines the default TTL.

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

### -VirtualizationInstance
Specifies the virtualization instance in which the zone will be added.
A virtualization instance is logical partition in a DNS Server, which is capable of independently hosting zones and zone scopes.
Same name zones and zone scopes can be hosted in different virtualization instances.
This parameter is optional and if not provided it will add the zone into the default virtualization instance which is functionally equivalent to a standard DNS server.

```yaml
Type: String
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

### -ZoneName
Specifies the name of a reverse lookup zone.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ZoneScope
Specifies the name of a zone scope.

```yaml
Type: String
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

### System.Management.ManagementBaseObject

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#DnsServerResourceRecord
The DnsServerResourceRecord object contains the following fields:

- **DistinguishedName**
- **HostName**
- **RecordClass**
- **RecordData**
- **RecordType**
- **Timestamp**
- **TimeToLive**
- **PtrDomainName**

## NOTES

## RELATED LINKS

