---
external help file: DnsServer_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: 95EDD405-167D-42AA-9C67-72624E9EA404
manager: dansimp
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Add-DnsServerResourceRecordMX

## SYNOPSIS
Adds an MX resource record to a DNS server.

## SYNTAX

```
Add-DnsServerResourceRecordMX [-ZoneName] <String> [-Name] <String> [-MailExchange] <String>
 [-Preference] <UInt16> [-AgeRecord] [-AllowUpdateAny] [-AsJob] [-CimSession <CimSession[]>]
 [-ComputerName <String>] [-PassThru] [-ThrottleLimit <Int32>] [-TimeToLive <TimeSpan>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Add-DnsServerResourceRecordMX** cmdlet adds a Mail Exchanger (MX) resource record to a Domain Name System (DNS) zone.

The MX resource record provides the name for a mail server for a domain.
If there are multiple MX resource records for a domain, the client attempts to contact mail servers in the order of preference from lowest value to highest value.

## EXAMPLES

### Example 1: Add an MX resource record
```
PS C:\> Add-DnsServerResourceRecordMX -Preference 10  -Name "." -TimeToLive 01:00:00 -MailExchange "mail.contoso.com" -ZoneName "contoso.com"
```

This command adds an MX record named RecordNameMX for the zone western.contoso.com with a preference of 123.
The mail exchanger is MAILSrv1.

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

### -MailExchange
Specifies an FQDN for a mail exchanger.
This value must resolve to a corresponding host (A) resource record.

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

### -Name
Specifies the name of the host or child domain for the mail exchange record.
To add an MX resource record for the parent domain, specify a dot (.)..

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

### -Preference
Specifies a priority, from 0 to 65535, for this MX resource record.
A service attempts to contact mail servers in the order of preference from lowest priority value to highest priority value.

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases: 

Required: True
Position: 5
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

### -ZoneName
Specifies the name of a DNS zone.

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

### Microsoft.Management.Infrastructure.CimInstance#DnsServerResourceRecord

## NOTES

## RELATED LINKS



