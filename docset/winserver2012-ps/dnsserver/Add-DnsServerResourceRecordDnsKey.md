---
external help file: DnsServer_Cmdlets.xml
Module Name: DnsServer
online version: https://docs.microsoft.com/powershell/module/dnsserver/add-dnsserverresourcerecorddnskey?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Add-DnsServerResourceRecordDnsKey

## SYNOPSIS
Adds a type DNSKEY resource record to a DNS zone.

## SYNTAX

```
Add-DnsServerResourceRecordDnsKey [-ZoneName] <String> [-Name] <String> [-CryptoAlgorithm] <String>
 [-Base64Data] <String> [-AgeRecord] [-AsJob] [-CimSession <CimSession[]>] [-ComputerName <String>]
 [-KeyProtocol <String>] [-PassThru] [-SecureEntryPoint] [-ThrottleLimit <Int32>] [-TimeToLive <TimeSpan>]
 [-ZoneKey] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Add-DnsServerResourceRecordDNSKEY** cmdlet adds DNSKEY resource record to a Domain Name System (DNS) server.
DNSKEY is a DNS Security Extensions (DNSSEC) element that stores a public key.
You most often use this cmdlet to add DNSKEY records to the TrustAnchors zone.

The **AgeRecord** parameter is not relevant for DS resource records.

If you do not specify either **SecureEntryPoint** or **ZoneSigningKey**, the cmdlet creates a trust anchor with the Secure Entry Point (SEP) bit set.

## EXAMPLES

### Example 1: Add a DNSKEY resource record to a different computer
```
PS C:\>$DNSKEYS = Get-DnsServerResourceRecord -RRType DnsKey -ZoneName "contoso.com" -ComputerName "dnsserver.contoso.com"

PS C:\>$DNSKEYS | %{ $_.RecordData | Add-DnsServerResourceRecordDnsKey -ZoneName "TrustAnchors" -Name  "contoso.com"  -ComputerName "dnsresolver.contoso.com" }
```

This example adds a DNSKEY resource record of the zone named contoso.com from the server named dnsserver.contoso.com to the server named dnsresolver.contoso.com.

The first command gets the DNSKEY resource record and stores it in the variable named **$DNSKEYS**.

The second command gets the DNSKEY resource record from **$DSNKEYS** and stores the resource record in the zone named TrustAnchors on the server named dnsresolver.contoso.com.

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

### -Base64Data
Specifies key data for this resource record.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 5
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

### -CryptoAlgorithm
Specifies the cryptographic algorithm the server uses to generate keys.
The acceptable values for this parameter are:

- RsaSha1
- RsaSha256
- RsaSha512
- RsaSha1NSec3
- ECDsaP256Sha256
- ECDsaP384Sha384

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

### -KeyProtocol
Specifies the key protocol for this resource record.
The only value for this parameter is DnsSec.

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

### -Name
Specifies the name of the resource record that this cmdlet adds to the DNS server.

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

### -SecureEntryPoint
Specifies whether the key is a secure entry point, as defined in RFC 3757.

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

### -ZoneKey
Specifies whether you can use this key to sign the zone.
This key can be either a Zone Signing Key (ZSK) or a Key Signing Key (KSK).

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

