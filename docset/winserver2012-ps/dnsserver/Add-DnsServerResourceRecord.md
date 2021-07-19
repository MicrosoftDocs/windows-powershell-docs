---
external help file: DnsServer_Cmdlets.xml
Module Name: DnsServer
online version: https://docs.microsoft.com/powershell/module/dnsserver/add-dnsserverresourcerecord?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Add-DnsServerResourceRecord

## SYNOPSIS
Adds a resource record of a specified type to a specified DNS zone.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Add-DnsServerResourceRecord [-ZoneName] <String> [-AllowUpdateAny] [-AsJob] [-CimSession <CimSession[]>]
 [-ComputerName <String>] [-Force] [-PassThru] [-ThrottleLimit <Int32>] -InputObject <CimInstance> [-Confirm]
 [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Add-DnsServerResourceRecord [-ZoneName] <String> [-Name] <String> [-A] [-AgeRecord] [-AllowUpdateAny] [-AsJob]
 [-CimSession <CimSession[]>] [-ComputerName <String>] [-CreatePtr] [-PassThru] [-ThrottleLimit <Int32>]
 [-TimeToLive <TimeSpan>] -IPv4Address <IPAddress> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Add-DnsServerResourceRecord [-ZoneName] <String> [-Name] <String> [-AAAA] [-AgeRecord] [-AllowUpdateAny]
 [-AsJob] [-CimSession <CimSession[]>] [-ComputerName <String>] [-CreatePtr] [-PassThru]
 [-ThrottleLimit <Int32>] [-TimeToLive <TimeSpan>] -IPv6Address <IPAddress> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_4
```
Add-DnsServerResourceRecord [-ZoneName] <String> [-Name] <String> [-Atma] [-AgeRecord] [-AllowUpdateAny]
 [-AsJob] [-CimSession <CimSession[]>] [-ComputerName <String>] [-PassThru] [-ThrottleLimit <Int32>]
 [-TimeToLive <TimeSpan>] -Address <String> -AddressType <String> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_5
```
Add-DnsServerResourceRecord [-ZoneName] <String> [-Name] <String> [-Afsdb] [-AgeRecord] [-AllowUpdateAny]
 [-AsJob] [-CimSession <CimSession[]>] [-ComputerName <String>] [-PassThru] [-ThrottleLimit <Int32>]
 [-TimeToLive <TimeSpan>] -ServerName <String> -SubType <UInt16> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_6
```
Add-DnsServerResourceRecord [-ZoneName] <String> [-Name] <String> [-Ptr] [-AgeRecord] [-AllowUpdateAny]
 [-AsJob] [-CimSession <CimSession[]>] [-ComputerName <String>] [-PassThru] [-ThrottleLimit <Int32>]
 [-TimeToLive <TimeSpan>] -PtrDomainName <String> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_7
```
Add-DnsServerResourceRecord [-ZoneName] <String> [-Name] <String> [-Txt] [-AgeRecord] [-AllowUpdateAny]
 [-AsJob] [-CimSession <CimSession[]>] [-ComputerName <String>] [-PassThru] [-ThrottleLimit <Int32>]
 [-TimeToLive <TimeSpan>] -DescriptiveText <String> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_8
```
Add-DnsServerResourceRecord [-ZoneName] <String> [-Name] <String> [-Srv] [-AgeRecord] [-AllowUpdateAny]
 [-AsJob] [-CimSession <CimSession[]>] [-ComputerName <String>] [-PassThru] [-ThrottleLimit <Int32>]
 [-TimeToLive <TimeSpan>] -DomainName <String> -Port <UInt16> -Priority <UInt16> -Weight <UInt16> [-Confirm]
 [-WhatIf]
```

### UNNAMED_PARAMETER_SET_9
```
Add-DnsServerResourceRecord [-ZoneName] <String> [-Name] <String> [-RT] [-AgeRecord] [-AllowUpdateAny] [-AsJob]
 [-CimSession <CimSession[]>] [-ComputerName <String>] [-PassThru] [-ThrottleLimit <Int32>]
 [-TimeToLive <TimeSpan>] -IntermediateHost <String> -Preference <UInt16> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_10
```
Add-DnsServerResourceRecord [-ZoneName] <String> [-Name] <String> [-Wks] [-AgeRecord] [-AllowUpdateAny]
 [-AsJob] [-CimSession <CimSession[]>] [-ComputerName <String>] [-PassThru] [-ThrottleLimit <Int32>]
 [-TimeToLive <TimeSpan>] -InternetAddress <IPAddress> -InternetProtocol <String> -Service <String[]>
 [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_11
```
Add-DnsServerResourceRecord [-ZoneName] <String> [-Name] <String> [-MX] [-AgeRecord] [-AllowUpdateAny] [-AsJob]
 [-CimSession <CimSession[]>] [-ComputerName <String>] [-PassThru] [-ThrottleLimit <Int32>]
 [-TimeToLive <TimeSpan>] -MailExchange <String> -Preference <UInt16> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_12
```
Add-DnsServerResourceRecord [-ZoneName] <String> [-Name] <String> [-Isdn] [-AgeRecord] [-AllowUpdateAny]
 [-AsJob] [-CimSession <CimSession[]>] [-ComputerName <String>] [-PassThru] [-ThrottleLimit <Int32>]
 [-TimeToLive <TimeSpan>] -IsdnNumber <String> -IsdnSubAddress <String> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_13
```
Add-DnsServerResourceRecord [-ZoneName] <String> [-Name] <String> [-HInfo] [-AgeRecord] [-AllowUpdateAny]
 [-AsJob] [-CimSession <CimSession[]>] [-ComputerName <String>] [-PassThru] [-ThrottleLimit <Int32>]
 [-TimeToLive <TimeSpan>] -Cpu <String> -OperatingSystem <String> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_14
```
Add-DnsServerResourceRecord [-ZoneName] <String> [-Name] <String> [-DName] [-AgeRecord] [-AllowUpdateAny]
 [-AsJob] [-CimSession <CimSession[]>] [-ComputerName <String>] [-PassThru] [-ThrottleLimit <Int32>]
 [-TimeToLive <TimeSpan>] -DomainNameAlias <String> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_15
```
Add-DnsServerResourceRecord [-ZoneName] <String> [-Name] <String> [-DhcId] [-AgeRecord] [-AllowUpdateAny]
 [-AsJob] [-CimSession <CimSession[]>] [-ComputerName <String>] [-PassThru] [-ThrottleLimit <Int32>]
 [-TimeToLive <TimeSpan>] -DhcpIdentifier <String> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_16
```
Add-DnsServerResourceRecord [-ZoneName] <String> [-Name] <String> [-CName] [-AgeRecord] [-AllowUpdateAny]
 [-AsJob] [-CimSession <CimSession[]>] [-ComputerName <String>] [-PassThru] [-ThrottleLimit <Int32>]
 [-TimeToLive <TimeSpan>] -HostNameAlias <String> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_17
```
Add-DnsServerResourceRecord [-ZoneName] <String> [-Name] <String> [-NS] [-AgeRecord] [-AllowUpdateAny] [-AsJob]
 [-CimSession <CimSession[]>] [-ComputerName <String>] [-PassThru] [-ThrottleLimit <Int32>]
 [-TimeToLive <TimeSpan>] -NameServer <String> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_18
```
Add-DnsServerResourceRecord [-ZoneName] <String> [-Name] <String> [-X25] [-AgeRecord] [-AllowUpdateAny]
 [-AsJob] [-CimSession <CimSession[]>] [-ComputerName <String>] [-PassThru] [-ThrottleLimit <Int32>]
 [-TimeToLive <TimeSpan>] -PsdnAddress <String> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_19
```
Add-DnsServerResourceRecord [-ZoneName] <String> [-Name] <String> [-RP] [-AgeRecord] [-AllowUpdateAny] [-AsJob]
 [-CimSession <CimSession[]>] [-ComputerName <String>] [-PassThru] [-ThrottleLimit <Int32>]
 [-TimeToLive <TimeSpan>] -Description <String> -ResponsiblePerson <String> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_20
```
Add-DnsServerResourceRecord [-ZoneName] <String> [-WinsR] [-AsJob] [-CimSession <CimSession[]>]
 [-ComputerName <String>] [-Force] [-PassThru] [-Replicate] [-ThrottleLimit <Int32>] -CacheTimeout <TimeSpan>
 -LookupTimeout <TimeSpan> -ResultDomain <String> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_21
```
Add-DnsServerResourceRecord [-ZoneName] <String> [-Wins] [-AsJob] [-CimSession <CimSession[]>]
 [-ComputerName <String>] [-Force] [-PassThru] [-Replicate] [-ThrottleLimit <Int32>] -CacheTimeout <TimeSpan>
 -LookupTimeout <TimeSpan> -WinsServers <IPAddress[]> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Add-DnsServerResourceRecord** cmdlet adds a resource record for a Domain Name System (DNS) zone on a DNS server.
You can add different types of resource records.
Use different switches for different record types.
For more information about resource records, see Managing Resource Recordshttp://technet.microsoft.com/en-us/library/cc754308.aspx (http://technet.microsoft.com/en-us/library/cc754308.aspx).

By using this cmdlet, you can change a value for a record, configure whether a record has a time stamp, whether any authenticated user can update a record with the same owner name, and change lookup timeout values, Windows Internet Name Service (WINS) cache settings, and replication settings.

## EXAMPLES

### Example 1: Add an A record
```
PS C:\>Add-DnsServerResourceRecord -ZoneName "Contoso.com" -A -Name "Host34" -AllowUpdateAny -IPv4Address "10.17.1.34" -TimeToLive 01:00:00 -AgeRecord
```

This command adds an A record that is named Host34 in the zone contoso.com with the specified IP address.
The command uses the **AllowUpdateAny** switch to allow any authenticated user to update the record.
It specifies a TTL value and enables a time stamp for the record.

### Example 2: Add an A resource record under the Admin noderesource
```
PS C:\> Add-DnsServerResourceRecord -ZoneName "Contoso.com" -A -Name "Host21.admin" -IPv4Address "10.17.1.21"
VERBOSE: Adding DNS resource record host21.admin of type A in zone contoso.com on ROOT server.
VERBOSE: Adding DNS resource record host21.admin of type A in zone contoso.com on ROOT server.
HostName                  RecordType Timestamp            TimeToLive      RecordData

--------                  ---------- ---------            ----------      ----------

host21.admin              A          0                    01:00:00        10.17.1.74
HostName                  RecordType Timestamp            TimeToLive      RecordData

--------                  ---------- ---------            ----------      ----------

host21.admin              A          0                    01:00:00        10.17.1.74
```

This command adds an A record for Host21 under the Admin node of Contoso.com.

### Example 3: Add an AAAA resource record resource
```
PS C:\>Add-DnsServerResourceRecord -AAAA -Name "Host73" -ZoneName "Contoso.com" -AllowUpdateAny -IPv6Address "3ffe::1" -TimeToLive 01:00:00 -AgeRecord
```

This command adds an AAAA record.
The command specifies **AllowUpdateAny**, a TTL value, and enables a time stamp for the record.

### Example 4: Add a CName CNAME resource recordCNAME
```
PS C:\>Add-DnsServerResourceRecord -CName -Name "labhost34" -HostNameAlias "Host34.lab.contoso.com" -ZoneName "Contoso.com" -AllowUpdateAny  -TimeToLive 01:00:00
```

This command adds a CNAME resource record.
The command specifies **AllowUpdateAny** and a TTL value.

### Example 5: Add a pointer PTR resource recordPTR resource
```
PS C:\>Add-DnsServerResourceRecord -Name "77" -Ptr -ZoneName "0.168.192.in-addr.arpa" -AllowUpdateAny -PtrDomainName "host77.contoso.com"
```

This command adds a pointer record named host77.contoso.com for the IP address 192.168.0.77 to the reverse lookup zone 0.168.192.in-addr.arpa..

### Example 6: Add an MX resource record
```
PS C:\>Add-DnsServerResourceRecord -Name ".-MX -ZoneName "contoso.com" -MailExchange "mail.contoso.com" -Preference 10
```

This command adds an MX resource record for the contoso.com zone with a preference of 10.

### Example 7: Add an SRV resource record
```
PS C:\>Add-DnsServerResourceRecord -Srv -Name "sip" -ZoneName "contoso.com" -DomainName "sipserver1.contoso.com" -Priority 0 -Weight 0 -Port 5060
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
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases:

Required: True
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AAAA
Indicates that the record that this cmdlet adds to the DNS server is an AAAA resource record.
An AAAA resource record maps a host name to an IPv6 address.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases:

Required: True
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Address
Specifies a byte array that contains the asynchronous transfer mode (ATM) address of the owner to which this resource record object pertains.
The **AddressType** parameter specifies the format of the byte array.
The first 4 bytes of the array store the size of the octet string.
The most significant byte is byte 0.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_4
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
Parameter Sets: UNNAMED_PARAMETER_SET_4
Aliases:

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
Parameter Sets: UNNAMED_PARAMETER_SET_5
Aliases:

Required: True
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AgeRecord
Indicates that the DNS server uses a time stamp for the resource record that this cmdlet adds.
A DNS server can scavenge resource records that have become stale based on a time stamp.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_3, UNNAMED_PARAMETER_SET_4, UNNAMED_PARAMETER_SET_5, UNNAMED_PARAMETER_SET_6, UNNAMED_PARAMETER_SET_7, UNNAMED_PARAMETER_SET_8, UNNAMED_PARAMETER_SET_9, UNNAMED_PARAMETER_SET_10, UNNAMED_PARAMETER_SET_11, UNNAMED_PARAMETER_SET_12, UNNAMED_PARAMETER_SET_13, UNNAMED_PARAMETER_SET_14, UNNAMED_PARAMETER_SET_15, UNNAMED_PARAMETER_SET_16, UNNAMED_PARAMETER_SET_17, UNNAMED_PARAMETER_SET_19
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_18
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
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases:

Required: False
Position: Named
Default value: FALSE
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_3, UNNAMED_PARAMETER_SET_4, UNNAMED_PARAMETER_SET_5, UNNAMED_PARAMETER_SET_6, UNNAMED_PARAMETER_SET_7, UNNAMED_PARAMETER_SET_8, UNNAMED_PARAMETER_SET_9, UNNAMED_PARAMETER_SET_10, UNNAMED_PARAMETER_SET_11, UNNAMED_PARAMETER_SET_12, UNNAMED_PARAMETER_SET_13, UNNAMED_PARAMETER_SET_14, UNNAMED_PARAMETER_SET_15, UNNAMED_PARAMETER_SET_16, UNNAMED_PARAMETER_SET_17, UNNAMED_PARAMETER_SET_18, UNNAMED_PARAMETER_SET_19
Aliases:

Required: False
Position: Named
Default value: FALSE
Accept pipeline input: False
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

### -Atma
Indicates that the record that this cmdlet adds to the DNS server is an ATM address resource record.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_4
Aliases:

Required: True
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CacheTimeout
Specifies how long, in seconds, that a DNS server caches a response from a WINS server.

```yaml
Type: TimeSpan
Parameter Sets: UNNAMED_PARAMETER_SET_20, UNNAMED_PARAMETER_SET_21
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -CName
Indicates that the record that this cmdlet adds to the DNS server is a canonical name (CNAME) resource record.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_16
Aliases:

Required: True
Position: 4
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

### -Cpu
Specifies the CPU type of a DNS server.
You can find the CPU type in a host information (HINFO) resource record.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_13
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
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Description
Specifies text to describe the person or people that are responsible for the domain.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_19
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
Parameter Sets: UNNAMED_PARAMETER_SET_7
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
Parameter Sets: UNNAMED_PARAMETER_SET_15
Aliases:

Required: True
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DhcpIdentifier
Specifies a public key that is associated with an FQDN, as described in section 3 of RFC 2535.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_15
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DName
Indicates that the record that this cmdlet adds to the DNS server is a domain alias (DNAME) resource record on a DNS server.
A DNAME resource record renames the root and all descendants in a domain namespace subtree and provides nonterminal domain name redirection.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_14
Aliases:

Required: True
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DomainName
Specifies the name of a domain.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_8
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
Parameter Sets: UNNAMED_PARAMETER_SET_14
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
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_20, UNNAMED_PARAMETER_SET_21
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
Parameter Sets: UNNAMED_PARAMETER_SET_13
Aliases:

Required: True
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HostNameAlias
Specifies a canonical name target for a CNAME record.
This must be a fully qualified domain name (FQDN).

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_16
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
This parameter takes an object of type **DnsServerResourceRecord**.

```yaml
Type: CimInstance
Parameter Sets: UNNAMED_PARAMETER_SET_1
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
Parameter Sets: UNNAMED_PARAMETER_SET_9
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
Parameter Sets: UNNAMED_PARAMETER_SET_10
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
Parameter Sets: UNNAMED_PARAMETER_SET_10
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
Parameter Sets: UNNAMED_PARAMETER_SET_2
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
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases:

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
Parameter Sets: UNNAMED_PARAMETER_SET_12
Aliases:

Required: True
Position: 4
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
Parameter Sets: UNNAMED_PARAMETER_SET_12
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
Parameter Sets: UNNAMED_PARAMETER_SET_12
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
Parameter Sets: UNNAMED_PARAMETER_SET_20, UNNAMED_PARAMETER_SET_21
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MailExchange
Specifies the FQDN of the host that is acting as a mail exchanger for the owner.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_11
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
Parameter Sets: UNNAMED_PARAMETER_SET_11
Aliases:

Required: True
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of a DNS server resource record object.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_3, UNNAMED_PARAMETER_SET_4, UNNAMED_PARAMETER_SET_5, UNNAMED_PARAMETER_SET_6, UNNAMED_PARAMETER_SET_7, UNNAMED_PARAMETER_SET_8, UNNAMED_PARAMETER_SET_9, UNNAMED_PARAMETER_SET_10, UNNAMED_PARAMETER_SET_11, UNNAMED_PARAMETER_SET_12, UNNAMED_PARAMETER_SET_13, UNNAMED_PARAMETER_SET_14, UNNAMED_PARAMETER_SET_15, UNNAMED_PARAMETER_SET_16, UNNAMED_PARAMETER_SET_17, UNNAMED_PARAMETER_SET_18, UNNAMED_PARAMETER_SET_19
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NameServer
Specifies the name server of a domain.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_17
Aliases:

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
Parameter Sets: UNNAMED_PARAMETER_SET_17
Aliases:

Required: True
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OperatingSystem
Specifies the operating system identifier of a DNS server.
You can find the operating system identifier in a HINFO resource record.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_13
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
Parameter Sets: UNNAMED_PARAMETER_SET_8
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
Parameter Sets: UNNAMED_PARAMETER_SET_9, UNNAMED_PARAMETER_SET_11
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
Parameter Sets: UNNAMED_PARAMETER_SET_8
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
Parameter Sets: UNNAMED_PARAMETER_SET_18
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
Parameter Sets: UNNAMED_PARAMETER_SET_6
Aliases:

Required: True
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PtrDomainName
Specifies the FQDN of the host when you add a PTR resource record.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_6
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Replicate
Indicates that the DNS server allows WINS replication.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_20, UNNAMED_PARAMETER_SET_21
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
Parameter Sets: UNNAMED_PARAMETER_SET_19
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
Parameter Sets: UNNAMED_PARAMETER_SET_20
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
Parameter Sets: UNNAMED_PARAMETER_SET_19
Aliases:

Required: True
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RT
Indicates that the record that this cmdlet adds to the DNS server is a Route Through (RT) resource record.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_9
Aliases:

Required: True
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServerName
Specifies the subtype of a host AFS server.
For subtype 1 (value=1), the host has an AFS version 3.0 Volume Location Server for the named AFS cell.
For subtype 2 (value=2), the host has an authenticated name server holding the cell-root directory node for the named DCE/NCA cell.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_5
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
Parameter Sets: UNNAMED_PARAMETER_SET_10
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
Parameter Sets: UNNAMED_PARAMETER_SET_8
Aliases:

Required: True
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubType
Specifies whether the server is an AFS volume location server.
Use a value of 1 indicate that the server is an AFS version 3.0 volume location server for the specified AFS cell.
Use a value of 2 to indicate that the server is an authenticated name server that holds the cell-root directory node for the server that uses either Open Software Foundation's (OSF) DCE authenticated cell-naming system or HP/Apollo's Network Computing Architecture (NCA).

For more information about server subtypes, see [RFC 1183](https://www.ietf.org/rfc/rfc1183.txt).

```yaml
Type: UInt16
Parameter Sets: UNNAMED_PARAMETER_SET_5
Aliases:

Required: True
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

### -TimeToLive
Specifies the Time to Live (TTL) value, in seconds, for a resource record.
Other DNS servers use this length of time to determine how long to cache a record.

```yaml
Type: TimeSpan
Parameter Sets: UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_3, UNNAMED_PARAMETER_SET_4, UNNAMED_PARAMETER_SET_5, UNNAMED_PARAMETER_SET_6, UNNAMED_PARAMETER_SET_7, UNNAMED_PARAMETER_SET_8, UNNAMED_PARAMETER_SET_9, UNNAMED_PARAMETER_SET_10, UNNAMED_PARAMETER_SET_11, UNNAMED_PARAMETER_SET_12, UNNAMED_PARAMETER_SET_13, UNNAMED_PARAMETER_SET_14, UNNAMED_PARAMETER_SET_15, UNNAMED_PARAMETER_SET_16, UNNAMED_PARAMETER_SET_17, UNNAMED_PARAMETER_SET_18, UNNAMED_PARAMETER_SET_19
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
Parameter Sets: UNNAMED_PARAMETER_SET_7
Aliases:

Required: True
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Weight
Specifies a value for the weight of the target host for a resource record.
You can use this parameter when you have multiple hosts that have an identical priority.
Use of the host is proportional to its weight.

```yaml
Type: UInt16
Parameter Sets: UNNAMED_PARAMETER_SET_8
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Wins
Indicates that the record that this cmdlet adds to the DNS server is a WINS resource record.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_21
Aliases:

Required: True
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WinsR
Indicates that the record that this cmdlet adds to the DNS server is a WINS reverse (WinsR) resource record.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_20
Aliases:

Required: True
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WinsServers
Specifies one or more IP addresses of WINS servers that you want to use for a resource record.

```yaml
Type: IPAddress[]
Parameter Sets: UNNAMED_PARAMETER_SET_21
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
Parameter Sets: UNNAMED_PARAMETER_SET_10
Aliases:

Required: True
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -X25
Indicates that the record that this cmdlet adds to the DNS server is an X25 resource record.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_18
Aliases:

Required: True
Position: 4
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

[RFC 2535](http://www.ietf.org/rfc/rfc2535.txt)

[RFC 1183](https://www.ietf.org/rfc/rfc1183.txt)

[Show-DnsServerCache](./Show-DnsServerCache.md)

[Set-DnsServerZoneAging](./Set-DnsServerZoneAging.md)
