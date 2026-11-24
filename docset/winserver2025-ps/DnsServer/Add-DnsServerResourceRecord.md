---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DnsServerResourceRecord_v1.0.0.cdxml-help.xml
Module Name: DnsServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dnsserver/add-dnsserverresourcerecord?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-DnsServerResourceRecord
---

# Add-DnsServerResourceRecord

## SYNOPSIS
Adds a resource record of a specified type to a specified DNS zone.

## SYNTAX

### InputObject (Default)
```
Add-DnsServerResourceRecord [-ZoneName] <String> [-ComputerName <String>] [-PassThru] [-ZoneScope <String>]
 [-VirtualizationInstance <String>] [-AllowUpdateAny] -InputObject <CimInstance> [-Force]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### X25
```
Add-DnsServerResourceRecord [-ZoneName] <String> [-ComputerName <String>] [-PassThru] [-ZoneScope <String>]
 [-VirtualizationInstance <String>] [-Name] <String> [-TimeToLive <TimeSpan>] [-AgeRecord] [-AllowUpdateAny]
 -PsdnAddress <String> [-X25] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### WKS
```
Add-DnsServerResourceRecord [-ZoneName] <String> [-ComputerName <String>] [-PassThru] [-ZoneScope <String>]
 [-VirtualizationInstance <String>] [-Name] <String> [-TimeToLive <TimeSpan>] [-AgeRecord] [-AllowUpdateAny]
 -InternetAddress <IPAddress> -InternetProtocol <String> -Service <String[]> [-Wks]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### WINSR
```
Add-DnsServerResourceRecord [-ZoneName] <String> [-ComputerName <String>] [-PassThru] [-ZoneScope <String>]
 [-VirtualizationInstance <String>] [-Force] -LookupTimeout <TimeSpan> [-Replicate] -CacheTimeout <TimeSpan>
 -ResultDomain <String> [-WinsR] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### WINS
```
Add-DnsServerResourceRecord [-ZoneName] <String> [-ComputerName <String>] [-PassThru] [-ZoneScope <String>]
 [-VirtualizationInstance <String>] [-Force] -LookupTimeout <TimeSpan> [-Replicate] -WinsServers <IPAddress[]>
 -CacheTimeout <TimeSpan> [-Wins] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### Unknown
```
Add-DnsServerResourceRecord [-ZoneName] <String> [-ComputerName <String>] [-PassThru] [-ZoneScope <String>]
 [-VirtualizationInstance <String>] [-Name] <String> [-TimeToLive <TimeSpan>] [-AgeRecord] [-AllowUpdateAny]
 [-Type] <UInt16> [-RecordData] <String> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### TXT
```
Add-DnsServerResourceRecord [-ZoneName] <String> [-ComputerName <String>] [-PassThru] [-ZoneScope <String>]
 [-VirtualizationInstance <String>] [-Name] <String> [-TimeToLive <TimeSpan>] [-AgeRecord] [-AllowUpdateAny]
 -DescriptiveText <String> [-Txt] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### TLSA
```
Add-DnsServerResourceRecord [-ZoneName] <String> [-ComputerName <String>] [-PassThru] [-ZoneScope <String>]
 [-VirtualizationInstance <String>] [[-Name] <String>] [-TimeToLive <TimeSpan>] [-AgeRecord] [-AllowUpdateAny]
 [-TLSA] -CertificateUsage <String> -MatchingType <String> -Selector <String>
 -CertificateAssociationData <String> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### SRV
```
Add-DnsServerResourceRecord [-ZoneName] <String> [-ComputerName <String>] [-PassThru] [-ZoneScope <String>]
 [-VirtualizationInstance <String>] [-Name] <String> [-TimeToLive <TimeSpan>] [-AgeRecord] [-AllowUpdateAny]
 -DomainName <String> -Priority <UInt16> -Weight <UInt16> -Port <UInt16> [-Srv] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### RT
```
Add-DnsServerResourceRecord [-ZoneName] <String> [-ComputerName <String>] [-PassThru] [-ZoneScope <String>]
 [-VirtualizationInstance <String>] [-Name] <String> [-TimeToLive <TimeSpan>] [-AgeRecord] [-AllowUpdateAny]
 -Preference <UInt16> -IntermediateHost <String> [-RT] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### RP
```
Add-DnsServerResourceRecord [-ZoneName] <String> [-ComputerName <String>] [-PassThru] [-ZoneScope <String>]
 [-VirtualizationInstance <String>] [-Name] <String> [-TimeToLive <TimeSpan>] [-AgeRecord] [-AllowUpdateAny]
 -ResponsiblePerson <String> -Description <String> [-RP] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### PTR
```
Add-DnsServerResourceRecord [-ZoneName] <String> [-ComputerName <String>] [-PassThru] [-ZoneScope <String>]
 [-VirtualizationInstance <String>] [-Name] <String> [-TimeToLive <TimeSpan>] [-AgeRecord] [-AllowUpdateAny]
 -PtrDomainName <String> [-Ptr] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### NS
```
Add-DnsServerResourceRecord [-ZoneName] <String> [-ComputerName <String>] [-PassThru] [-ZoneScope <String>]
 [-VirtualizationInstance <String>] [-Name] <String> [-TimeToLive <TimeSpan>] [-AgeRecord] [-AllowUpdateAny]
 -NameServer <String> [-NS] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### MX
```
Add-DnsServerResourceRecord [-ZoneName] <String> [-ComputerName <String>] [-PassThru] [-ZoneScope <String>]
 [-VirtualizationInstance <String>] [-Name] <String> [-TimeToLive <TimeSpan>] [-AgeRecord] [-AllowUpdateAny]
 -MailExchange <String> -Preference <UInt16> [-MX] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ISDN
```
Add-DnsServerResourceRecord [-ZoneName] <String> [-ComputerName <String>] [-PassThru] [-ZoneScope <String>]
 [-VirtualizationInstance <String>] [-Name] <String> [-TimeToLive <TimeSpan>] [-AgeRecord] [-AllowUpdateAny]
 -IsdnNumber <String> -IsdnSubAddress <String> [-Isdn] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### HINFO
```
Add-DnsServerResourceRecord [-ZoneName] <String> [-ComputerName <String>] [-PassThru] [-ZoneScope <String>]
 [-VirtualizationInstance <String>] [-Name] <String> [-TimeToLive <TimeSpan>] [-AgeRecord] [-AllowUpdateAny]
 -Cpu <String> -OperatingSystem <String> [-HInfo] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### DNAME
```
Add-DnsServerResourceRecord [-ZoneName] <String> [-ComputerName <String>] [-PassThru] [-ZoneScope <String>]
 [-VirtualizationInstance <String>] [-Name] <String> [-TimeToLive <TimeSpan>] [-AgeRecord] [-AllowUpdateAny]
 -DomainNameAlias <String> [-DName] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### DHCID
```
Add-DnsServerResourceRecord [-ZoneName] <String> [-ComputerName <String>] [-PassThru] [-ZoneScope <String>]
 [-VirtualizationInstance <String>] [-Name] <String> [-TimeToLive <TimeSpan>] [-AgeRecord] [-AllowUpdateAny]
 -DhcpIdentifier <String> [-DhcId] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### CNAME
```
Add-DnsServerResourceRecord [-ZoneName] <String> [-ComputerName <String>] [-PassThru] [-ZoneScope <String>]
 [-VirtualizationInstance <String>] [-Name] <String> [-TimeToLive <TimeSpan>] [-AgeRecord] [-AllowUpdateAny]
 -HostNameAlias <String> [-CName] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### ATMA
```
Add-DnsServerResourceRecord [-ZoneName] <String> [-ComputerName <String>] [-PassThru] [-ZoneScope <String>]
 [-VirtualizationInstance <String>] [-Name] <String> [-TimeToLive <TimeSpan>] [-AgeRecord] [-AllowUpdateAny]
 -Address <String> -AddressType <String> [-Atma] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### AFSDB
```
Add-DnsServerResourceRecord [-ZoneName] <String> [-ComputerName <String>] [-PassThru] [-ZoneScope <String>]
 [-VirtualizationInstance <String>] [-Name] <String> [-TimeToLive <TimeSpan>] [-AgeRecord] [-AllowUpdateAny]
 -SubType <UInt16> -ServerName <String> [-Afsdb] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### AAAA
```
Add-DnsServerResourceRecord [-ZoneName] <String> [-ComputerName <String>] [-PassThru] [-ZoneScope <String>]
 [-VirtualizationInstance <String>] [-CreatePtr] [-Name] <String> [-TimeToLive <TimeSpan>] [-AgeRecord]
 [-AllowUpdateAny] -IPv6Address <IPAddress> [-AAAA] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### A
```
Add-DnsServerResourceRecord [-ZoneName] <String> [-ComputerName <String>] [-PassThru] [-ZoneScope <String>]
 [-VirtualizationInstance <String>] [-CreatePtr] -IPv4Address <IPAddress> [-Name] <String>
 [-TimeToLive <TimeSpan>] [-AgeRecord] [-AllowUpdateAny] [-A] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-DnsServerResourceRecord** cmdlet adds a resource record for a Domain Name System (DNS) zone on a DNS server.
You can add different types of resource records.
Use different switches for different record types.
For more information about resource records, see [Managing Resource Records](https://technet.microsoft.com/en-us/library/cc754308.aspx).

By using this cmdlet, you can change a value for a record, configure whether a record has a time stamp, whether any authenticated user can update a record with the same owner name, and change lookup timeout values, Windows Internet Name Service (WINS) cache settings, and replication settings.

## EXAMPLES

### Example 1: Add an A record
```
PS C:\> Add-DnsServerResourceRecord -ZoneName "Contoso.com" -A -Name "Host34" -AllowUpdateAny -IPv4Address "10.17.1.34" -TimeToLive 01:00:00 -AgeRecord
```

This command adds an A record that is named Host34 in the zone contoso.com with the specified IP address.
The command uses the **AllowUpdateAny** switch to allow any authenticated user to update the record.
It specifies a TTL value and enables a time stamp for the record.

### Example 2: Add an A resource record under the Admin node
```
PS C:\> Add-DnsServerResourceRecord -ZoneName "Contoso.com" -A -Name "Host21.admin" -IPv4Address "10.17.1.21"

VERBOSE: Adding DNS resource record host21.admin of type A in zone contoso.com on ROOT server.
HostName                  RecordType Timestamp            TimeToLive      RecordData
--------                  ---------- ---------            ----------      ----------
host21.admin              A          0                    01:00:00        10.17.1.74
```

This command adds an A record for Host21 under the Admin node of Contoso.com.

### Example 3: Add an AAAA resource record
```
PS C:\> Add-DnsServerResourceRecord -AAAA -Name "Host73" -ZoneName "Contoso.com" -AllowUpdateAny -IPv6Address "3ffe::1" -TimeToLive 01:00:00 -AgeRecord
```

This command adds an AAAA record.
The command specifies **AllowUpdateAny**, a TTL value, and enables a time stamp for the record.

### Example 4: Add a CNAME resource record
```
PS C:\> Add-DnsServerResourceRecord -CName -Name "labhost34" -HostNameAlias "Host34.lab.contoso.com" -ZoneName "Contoso.com" -AllowUpdateAny  -TimeToLive 01:00:00
```

This command adds a CNAME resource record.
The command specifies **AllowUpdateAny** and a TTL value.

### Example 5: Add a PTR resource record
```
PS C:\> Add-DnsServerResourceRecord -Name "77" -Ptr -ZoneName "0.168.192.in-addr.arpa" -AllowUpdateAny -PtrDomainName "host77.contoso.com"
```

This command adds a pointer record named host77.contoso.com for the IP address 192.168.0.77 to the reverse lookup zone 0.168.192.in-addr.arpa..

### Example 6: Add an MX resource record
```
PS C:\> Add-DnsServerResourceRecord -Name "." -MX -ZoneName "contoso.com" -MailExchange "mail.contoso.com" -Preference 10
```

This command adds an MX resource record for the contoso.com zone with a preference of 10.

### Example 7: Add an SRV resource record
```
PS C:\> Add-DnsServerResourceRecord -Srv -Name "sip" -ZoneName "contoso.com" -DomainName "sipserver1.contoso.com" -Priority 0 -Weight 0 -Port 5060
```

This command adds a service locator (SRV) resource record for the _sip service on port 5060 with a weight and priority of 0 to the contoso.com domain.
The host that offers the service is sipserver1.contoso.com.

### Example 8: Add a multiline TXT resource record
```powershell
$dkim2 = "v=DKIM1;k=rsa;p=MIIBIjANBgkqhkiG9w0BAQEFAAOCAQ8AMIIBCgKCAQEAy6OAXCmjYT823gq+DXRjXdsypt7iepfl4pkvLRVN8wRwoND2Fk2aVlG+CitAeJ0nqWn7JAPjoTXpFtHnOWMN7ay/atQd+DcLLHfJkpRvsYSDQ1jkI2s7CkWF6G+nwLGJcNFndOdB8oawpppyESE7+DiZae8bDicaTK8oPU0J7iogeZ1fgvmutwNtNzZHiSgwF9euCiX6lTmGe+0oZ+gRUJnUmZevh//IZ+NyDkRV2kPxQBtM8brHUpRL1c11q/CA0kC6C3ku+Pqmf6A8CGT+qvlCeQ2lVqlBydQL5UjiixUEwkSrgUEKoKE2Hqw97WrDEJZqngtuqma9hWoAsKVbzwIDAQAB"
$dkim2_part1 = $dkim2.Substring(0,252)

$dkim2_part2 = $dkim2.Substring(252,$dkim2.Length - 252)

Add-DnsServerResourceRecord -DescriptiveText "$dkim2_part1`r`n$dkim_part2" -Name sea2048._domainkey -Txt -ZoneName $domain -TimeToLive 0:1:0:0
```

This command adds a multiline TXT resource record. The string is split into 252 character sets and the new line, which is two characters in Windows, is added at the end.

## PARAMETERS

### -A
Indicates that the record that this cmdlet adds to the DNS server is a host address (A) resource record.
An A resource record maps a host name to an IPv4 address.

```yaml
Type: SwitchParameter
Parameter Sets: A
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AAAA
Indicates that the record that this cmdlet adds to the DNS server is an AAAA resource record.
An AAAA resource record maps a host name to an IPv6 address.

```yaml
Type: SwitchParameter
Parameter Sets: AAAA
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Address
Specifies a byte array that contains the asynchronous transfer mode (ATM) address of the owner to which this resource record object pertains.
The *AddressType* parameter specifies the format of the byte array.
The first 4 bytes of the array store the size of the octet string.
The most significant byte is byte 0.

```yaml
Type: String
Parameter Sets: ATMA
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AddressType
Specifies the format of an ATM address in an ATM address (ATMA) resource record.
Valid values are: 0, for an ATM End System Address (AESA) format, and 1, for an E.164 address format.

```yaml
Type: String
Parameter Sets: ATMA
Aliases:
Accepted values: E164, AESA

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Afsdb
Indicates that the record that this cmdlet adds to the DNS server is an Andrew File System cell database server (AFSDB) resource record.
An AFSDB resource record gives the location of the AFS cell database server and uses DNS to map a DNS domain name to the name of an AFS cell database server.

```yaml
Type: SwitchParameter
Parameter Sets: AFSDB
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AgeRecord
Indicates that the DNS server uses a time stamp for the resource record that this cmdlet adds.
A DNS server can scavenge resource records that have become stale based on a time stamp.

```yaml
Type: SwitchParameter
Parameter Sets: X25, TLSA
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: SwitchParameter
Parameter Sets: WKS, Unknown, TXT, SRV, RT, RP, PTR, NS, MX, ISDN, HINFO, DNAME, DHCID, CNAME, ATMA, AFSDB, AAAA, A
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllowUpdateAny
Indicates that any authenticated user can update a resource record that has the same owner name.

```yaml
Type: SwitchParameter
Parameter Sets: InputObject, TLSA
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: SwitchParameter
Parameter Sets: X25, WKS, Unknown, TXT, SRV, RT, RP, PTR, NS, MX, ISDN, HINFO, DNAME, DHCID, CNAME, ATMA, AFSDB, AAAA, A
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

### -Atma
Indicates that the record that this cmdlet adds to the DNS server is an ATM address resource record.

```yaml
Type: SwitchParameter
Parameter Sets: ATMA
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CName
Indicates that the record that this cmdlet adds to the DNS server is a canonical name (CNAME) resource record.

```yaml
Type: SwitchParameter
Parameter Sets: CNAME
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CacheTimeout
Specifies how long, in seconds, that a DNS server caches a response from a WINS server.

```yaml
Type: TimeSpan
Parameter Sets: WINSR, WINS
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CertificateAssociationData
Specifies the certificate association data for a Transport Layer Security (TLS) authentication record.

```yaml
Type: String
Parameter Sets: TLSA
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CertificateUsage
Specifies the certificate usage TLS authentication record.

```yaml
Type: String
Parameter Sets: TLSA
Aliases:
Accepted values: CAConstraint, ServiceCertificateConstraint, TrustAnchorAssertion, DomainIssuedCertificate

Required: True
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

### -Cpu
Specifies the CPU type of a DNS server.
You can find the CPU type in a host information (HINFO) resource record.

```yaml
Type: String
Parameter Sets: HINFO
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CreatePtr
Indicates that the DNS server automatically creates an associated pointer (PTR) resource record for an A or AAAA record.
A PTR resource record maps an IP address to a host name.

```yaml
Type: SwitchParameter
Parameter Sets: AAAA
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: SwitchParameter
Parameter Sets: A
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DName
Indicates that the record that this cmdlet adds to the DNS server is a domain alias (DNAME) resource record on a DNS server.
A DNAME resource record renames the root and all descendants in a domain namespace subtree and provides nonterminal domain name redirection.

```yaml
Type: SwitchParameter
Parameter Sets: DNAME
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description
Specifies text to describe the person or people that are responsible for the domain.

```yaml
Type: String
Parameter Sets: RP
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DescriptiveText
Specifies additional text to describe a resource record on a DNS server. It is limited to 254 characters per line.

```yaml
Type: String
Parameter Sets: TXT
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DhcId
Indicates that the record that this cmdlet adds to the DNS server is a Dynamic Host Configuration Protocol Information (DHCID) resource record.

```yaml
Type: SwitchParameter
Parameter Sets: DHCID
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DhcpIdentifier
Specifies a public key that is associated with an FQDN, as described in section 3 of RFC 2535.

```yaml
Type: String
Parameter Sets: DHCID
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DomainName
Specifies the name of a domain.

```yaml
Type: String
Parameter Sets: SRV
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DomainNameAlias
Specifies the alias for a domain name.

```yaml
Type: String
Parameter Sets: DNAME
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Force
Adds a resource record without prompting you for confirmation.
By default, the cmdlet prompts you for confirmation before it proceeds.

```yaml
Type: SwitchParameter
Parameter Sets: InputObject, WINSR, WINS
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HInfo
Indicates that the record that this cmdlet adds to the DNS server is a host information (HINFO) resource record on a DNS server.

```yaml
Type: SwitchParameter
Parameter Sets: HINFO
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HostNameAlias
Specifies a canonical name target for a CNAME record.
This must be a fully qualified domain name (FQDN).

```yaml
Type: String
Parameter Sets: CNAME
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IPv4Address
Specifies the IPv4 address of a host.

```yaml
Type: IPAddress
Parameter Sets: A
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IPv6Address
Specifies the IPv6 address of a host.

```yaml
Type: IPAddress
Parameter Sets: AAAA
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InputObject
Specifies the input to this cmdlet.
You can use this parameter, or you can pipe the input to this cmdlet.

```yaml
Type: CimInstance
Parameter Sets: InputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -IntermediateHost
Specifies the FQDN of a host that routes packets to a destination host.

```yaml
Type: String
Parameter Sets: RT
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InternetAddress
Specifies the IP address of the owner of a resource record.

```yaml
Type: IPAddress
Parameter Sets: WKS
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InternetProtocol
Specifies the Internet Protocol (IP) for a resource record.
Valid values are: UDP or TCP.

```yaml
Type: String
Parameter Sets: WKS
Aliases:
Accepted values: UDP, TCP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Isdn
Indicates that the record that this cmdlet adds to the DNS server is an Integrated Services Digital Network (ISDN) resource record.

```yaml
Type: SwitchParameter
Parameter Sets: ISDN
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IsdnNumber
Specifies the number in the ISDN address that maps to the FQDN of a DNS server.
An ISDN address, which consists of a phone number and an optional subaddress, is located in an ISDN resource record.
The phone number can contain a country/region code, an area code, and a local phone number.

```yaml
Type: String
Parameter Sets: ISDN
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IsdnSubAddress
Specifies the number that is contained in an ISDN address that maps to the FQDN of a DNS server.
An ISDN address consists of a phone number and an optional subaddress and is located in an ISDN resource record.
The subaddress is an identifier that describes the ISDN subaddress encoding type.

```yaml
Type: String
Parameter Sets: ISDN
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LookupTimeout
Specifies the lookup time-out value for a resource record.

```yaml
Type: TimeSpan
Parameter Sets: WINSR, WINS
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MX
Indicates that the record that this cmdlet adds to the DNS server is a mail exchanger (MX) resource record.

```yaml
Type: SwitchParameter
Parameter Sets: MX
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MailExchange
Specifies the FQDN of the host that is acting as a mail exchanger for the owner.

```yaml
Type: String
Parameter Sets: MX
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MatchingType
Specifies the matching type for the record.
The acceptable values for this parameter are:

- ExactMatch
- Sha256Hash
- Sha512Hash

```yaml
Type: String
Parameter Sets: TLSA
Aliases:
Accepted values: ExactMatch, Sha256Hash, Sha512Hash

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NS
Indicates that the record that this cmdlet adds to the DNS server is a Name Server (NS) resource record on a DNS server.

```yaml
Type: SwitchParameter
Parameter Sets: NS
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of a DNS server resource record object.

```yaml
Type: String
Parameter Sets: X25, WKS, Unknown, TXT, SRV, RT, RP, PTR, NS, MX, ISDN, HINFO, DNAME, DHCID, CNAME, ATMA, AFSDB, AAAA, A
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: TLSA
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NameServer
Specifies the name server of a domain.

```yaml
Type: String
Parameter Sets: NS
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -OperatingSystem
Specifies the operating system identifier of a DNS server.
You can find the operating system identifier in a HINFO resource record.

```yaml
Type: String
Parameter Sets: HINFO
Aliases:

Required: True
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

### -Port
Specifies the port where the server listens for the service.

```yaml
Type: UInt16
Parameter Sets: SRV
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Preference
Specifies the priority for this resource record among other resource records that belong to the same owner, where a lower value has a higher priority.

```yaml
Type: UInt16
Parameter Sets: RT, MX
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Priority
Specifies the priority of a DNS server.
Clients try to contact the server that has the lowest priority.

```yaml
Type: UInt16
Parameter Sets: SRV
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PsdnAddress
Specifies the public switched data network (PSDN) address of the owner of a resource record.

```yaml
Type: String
Parameter Sets: X25
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Ptr
Indicates that the record that this cmdlet adds to the DNS server is a PTR resource record.

```yaml
Type: SwitchParameter
Parameter Sets: PTR
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PtrDomainName
Specifies the FQDN of the host when you add a PTR resource record.

```yaml
Type: String
Parameter Sets: PTR
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RP
Indicates that the record that this cmdlet adds to the DNS server is a Responsible Person (RP) resource record.

```yaml
Type: SwitchParameter
Parameter Sets: RP
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RT
Indicates that the record that this cmdlet adds to the DNS server is a Route Through (RT) resource record.

```yaml
Type: SwitchParameter
Parameter Sets: RT
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RecordData
Specifies the data contained in the resource record you want to add.

```yaml
Type: String
Parameter Sets: Unknown
Aliases:

Required: True
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Replicate
Indicates that the DNS server allows WINS replication.

```yaml
Type: SwitchParameter
Parameter Sets: WINSR, WINS
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResponsiblePerson
Specifies the FQDN for the domain mailbox name of the person who is responsible for the resource record.

When used together with the MR parameter set, this value specifies a mailbox that is the proper rename of the mailbox that is specified in the resource record's owner name.

```yaml
Type: String
Parameter Sets: RP
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResultDomain
Specifies the domain name to append to returned NetBIOS names.

```yaml
Type: String
Parameter Sets: WINSR
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Selector
Specifies a selector.

```yaml
Type: String
Parameter Sets: TLSA
Aliases:
Accepted values: FullCertificate, SubjectPublicKeyInfo

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServerName
Specifies the subtype of a host AFS server.
For subtype 1 (value=1), the host has an AFS version 3.0 Volume Location Server for the named AFS cell.
For subtype 2 (value=2), the host has an authenticated name server holding the cell-root directory node for the named DCE/NCA cell.

```yaml
Type: String
Parameter Sets: AFSDB
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Service
Specifies the service or services that are available for the current rewrite path.
It can also specify a particular protocol to use for a service.
Available services include Well-known Service (WKS) and NAPTR.

```yaml
Type: String[]
Parameter Sets: WKS
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Srv
Indicates that the record that this cmdlet adds to the DNS server is a Service (SRV) resource record.

```yaml
Type: SwitchParameter
Parameter Sets: SRV
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubType
Specifies whether the server is an AFS volume location server.
Use a value of 1 indicate that the server is an AFS version 3.0 volume location server for the specified AFS cell.
Use a value of 2 to indicate that the server is an authenticated name server that holds the cell-root directory node for the server that uses either Open Software Foundation's (OSF) DCE authenticated cell-naming system or HP/Apollo's Network Computing Architecture (NCA).

For more information about server subtypes, see [RFC 1183](http://www.ietf.org/rfc/rfc1183.txt).

```yaml
Type: UInt16
Parameter Sets: AFSDB
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TLSA
Indicates that the record that this cmdlet adds is a TLS authentication resource record.

```yaml
Type: SwitchParameter
Parameter Sets: TLSA
Aliases:

Required: True
Position: 3
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
Parameter Sets: X25, WKS, Unknown, TXT, SRV, RT, RP, PTR, NS, MX, ISDN, HINFO, DNAME, DHCID, CNAME, ATMA, AFSDB, AAAA, A
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: TimeSpan
Parameter Sets: TLSA
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Txt
Indicates that the record that this cmdlet adds to the DNS server is a TXT resource record.

```yaml
Type: SwitchParameter
Parameter Sets: TXT
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Type
Specifies the type of the resource record.

```yaml
Type: UInt16
Parameter Sets: Unknown
Aliases:

Required: True
Position: 3
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

### -Weight
Specifies a value for the weight of the target host for a resource record.
You can use this parameter when you have multiple hosts that have an identical priority.
Use of the host is proportional to its weight.

```yaml
Type: UInt16
Parameter Sets: SRV
Aliases:

Required: True
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

### -Wins
Indicates that the record that this cmdlet adds to the DNS server is a WINS resource record.

```yaml
Type: SwitchParameter
Parameter Sets: WINS
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WinsR
Indicates that the record that this cmdlet adds to the DNS server is a WINS reverse (WinsR) resource record.

```yaml
Type: SwitchParameter
Parameter Sets: WINSR
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WinsServers
Specifies one or more IP addresses of WINS servers that you want to use for a resource record.

```yaml
Type: IPAddress[]
Parameter Sets: WINS
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Wks
Indicates that the record that this cmdlet adds to the DNS server is WKS resource record.

```yaml
Type: SwitchParameter
Parameter Sets: WKS
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -X25
Indicates that the record that this cmdlet adds to the DNS server is an X25 resource record.

```yaml
Type: SwitchParameter
Parameter Sets: X25
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ZoneName
Specifies the name of a DNS zone.

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

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#DnsServerResourceRecord

## NOTES

## RELATED LINKS

[RFC 2535](http://www.ietf.org/rfc/rfc2535.txt)

[RFC 1183](http://www.ietf.org/rfc/rfc1183.txt)

[Show-DnsServerCache](./Show-DnsServerCache.md)

[Set-DnsServerZoneAging](./Set-DnsServerZoneAging.md)
