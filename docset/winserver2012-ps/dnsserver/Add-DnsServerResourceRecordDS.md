---
external help file: DnsServer_Cmdlets.xml
Module Name: DnsServer
online version: https://learn.microsoft.com/powershell/module/dnsserver/add-dnsserverresourcerecordds?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Add-DnsServerResourceRecordDS

## SYNOPSIS
Adds a type DS resource record to a DNS zone.

## SYNTAX

```
Add-DnsServerResourceRecordDS [-ZoneName] <String> [-Name] <String> [-KeyTag] <UInt16>
 [-CryptoAlgorithm] <String> [-DigestType] <String> [-Digest] <String> [-AgeRecord] [-AsJob]
 [-CimSession <CimSession[]>] [-ComputerName <String>] [-PassThru] [-ThrottleLimit <Int32>]
 [-TimeToLive <TimeSpan>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Add-DnsServerResourceRecordDS** cmdlet adds a Delegation Signer (DS) resource record to a specified Domain Name System (DNS) zone.

The **AgeRecord** parameter is not relevant for DS resource records.

## EXAMPLES

### Example 1: Import and add a DS record
```
PS C:\> $b = Get-DnsServerResourceRecord -RRType DS -ZoneName "contoso.com" -computerName "Server1"

PS C:\> $b[0].RecordData | Add-DnsServerResourceRecordDS -ZoneName "contoso.com" -Name "west02" -computerName "Server2"
```

This command imports a DS record from a zone named West02.contoso.com and adds it to the parent zone, contoso.com.

The first command gets the DS record and stores it in the variable named **$b**.

The second command gets the DS record from $b and adds it to contoso.com.

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
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Digest
Specifies DS digest data.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 7
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DigestType
Specifies the type of digest data.
The acceptable values for this parameter are:

- Sha1
- Sha256
- Sha384

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 6
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -KeyTag
Specifies a key tag.

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases: 

Required: True
Position: 4
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
Specifies the name of a DNS zone.
The cmdlet adds the record to this zone.

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

[Import-DnsServerResourceRecordDS](./Import-DnsServerResourceRecordDS.md)

