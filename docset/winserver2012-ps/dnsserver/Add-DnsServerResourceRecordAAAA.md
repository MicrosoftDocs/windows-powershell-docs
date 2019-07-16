---
external help file: DnsServer_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: E9733443-E45A-42AE-88D3-327F7EF59F87
manager: dansimp
ms.reviewer:
ms.author: v-anbarr
author: andreabarr
---

# Add-DnsServerResourceRecordAAAA

## SYNOPSIS
Adds a type AAAA resource record to a DNS server.

## SYNTAX

```
Add-DnsServerResourceRecordAAAA [-ZoneName] <String> [-Name] <String> [-IPv6Address] <IPAddress[]> [-AgeRecord]
 [-AllowUpdateAny] [-AsJob] [-CimSession <CimSession[]>] [-ComputerName <String>] [-CreatePtr] [-PassThru]
 [-ThrottleLimit <Int32>] [-TimeToLive <TimeSpan>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Add-DnsServerResourceRecordAAAA** cmdlet adds a specified host IPv6 address (AAAA) record to a specified Domain Name System (DNS) zone.
An AAAA record specifies an IPv6 address.

## EXAMPLES

### Example 1: Add a DNS record
```
PS C:\> Add-DnsServerResourceRecordAAAA -Name "host24" -ZoneName "contoso.com" -AllowUpdateAny -IPv6Address "3ffe::1" -TimeToLive 01:00:00
```

This example adds a type AAAA DNS record for a host named host24 in the zone named contoso.com.
The command specifies **AllowUpdateAny** and provides a TTL value.

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

### -CreatePtr
Indicates that the DNS server automatically creates an associated pointer (PTR) resource record for an AAAA record.
A PTR resource record maps an IP address to an FQDN.

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

### -IPv6Address
Specifies an array of IPv6 addresses.

```yaml
Type: IPAddress[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies a host name.

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
Specifies the name of the DNS zone to which you add the record.

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

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#DnsServerResourceRecord[]

## NOTES

## RELATED LINKS

[00000000-0000-0000-0000-000000000000](00000000-0000-0000-0000-000000000000)

