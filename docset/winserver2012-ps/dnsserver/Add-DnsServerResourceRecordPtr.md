---
external help file: DnsServer_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: B75110F1-585A-4A07-BA06-2894D861F311
manager: dansimp
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Add-DnsServerResourceRecordPtr

## SYNOPSIS
Adds a type PTR resource record to a DNS server.

## SYNTAX

```
Add-DnsServerResourceRecordPtr [-ZoneName] <String> [-Name] <String> [-PtrDomainName] <String> [-AgeRecord]
 [-AllowUpdateAny] [-AsJob] [-CimSession <CimSession[]>] [-ComputerName <String>] [-PassThru]
 [-ThrottleLimit <Int32>] [-TimeToLive <TimeSpan>] [-Confirm] [-WhatIf]
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
Because the command includes the **AgeRecord** parameter, a DNS server can scavenge this record.

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
Default value: False
Accept pipeline input: True (ByPropertyName)
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

### -ComputerName
Specifies a DNS server.
If you do not specify this parameter, the command runs on the local system.
You can specify an IP address or any value that resolves to an IP address, such as a fully qualified domain name (FQDN), host name, or NETBIOS name.

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

### -Name
Specifies part of the IP address for the host.
You can use either an IPv4 or IPv6 address.
For example, if you use an IPv4 class C reverse lookup zone, then **Name** specifies the last octet of the IP address.
If you use a class B reverse lookup zone, then **Name** specifies the last two octets.

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
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ThrottleLimit


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

### -ZoneName
Specifies the name of a reverse lookup zone.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### System.Management.ManagementBaseObject

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#DnsServerResourceRecord

## NOTES

## RELATED LINKS



