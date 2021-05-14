---
external help file: DnsServer_Cmdlets.xml
Module Name: DnsServer
online version: https://docs.microsoft.com/powershell/module/dnsserver/set-dnsserverdnsseczonesetting?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-DnsServerDnsSecZoneSetting

## SYNOPSIS
Changes settings for DNSSEC for a zone.

## SYNTAX

```
Set-DnsServerDnsSecZoneSetting [-ZoneName] <String> [[-DenialOfExistence] <String>] [-AsJob]
 [-CimSession <CimSession[]>] [-ComputerName <String>] [-DistributeTrustAnchor <String[]>]
 [-DnsKeyRecordSetTtl <TimeSpan>] [-DSRecordGenerationAlgorithm <String[]>] [-DSRecordSetTtl <TimeSpan>]
 [-EnableRfc5011KeyRollover <Boolean>] [-NSec3HashAlgorithm <String>] [-NSec3Iterations <UInt16>]
 [-NSec3OptOut <Boolean>] [-NSec3RandomSaltLength <Byte>] [-NSec3UserSalt <String>]
 [-ParentHasSecureDelegation <Boolean>] [-PassThru] [-PropagationTime <TimeSpan>]
 [-SecureDelegationPollingPeriod <TimeSpan>] [-SignatureInceptionOffset <TimeSpan>] [-ThrottleLimit <Int32>]
 [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Set-DnsServerDnsSecZoneSetting** cmdlet changes Domain Name System Security Extensions (DNSSEC) settings for the specified zone on a Domain Name System (DNS) server.

You can select which version of Next Secure (NSEC) to use to provide authenticated denial of existence.
Set the **DenialOfExistence** parameter to NSec or NSec3.
If you use NSec3, you can use either random salt or user-defined salt.

## EXAMPLES

### Example 1: Modify RFC 5011 settings
```
PS C:\> Set-DnsServerDnsSecZoneSetting -ZoneName "west01.contoso.com" -EnableRfc5011KeyRollover $true -PassThru -Verbose
```

This command modifies RFC 5011 settings for a zone named west01.contoso.com.
The example uses the **PassThru** parameter to produce output and the **Verbose** parameter to include all output.

## PARAMETERS

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

### -DenialOfExistence
Specifies which version of NSEC to use.
A DNS server uses this setting to provide signed proof of an unregistered name.

The acceptable values for this parameter are:

- NSec
- NSec3

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

### -DistributeTrustAnchor
Specifies an array of trust anchors that a DNS server distributes in Active Directory® Domain Services.
DNS servers do not distribute trust anchors by default.
If the DNS server is not also a domain controller, it adds trust anchors only to the local trust anchor store.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DnsKeyRecordSetTtl
Specifies a time-span object that represents the Time to Live (TTL) value of a DNS key record.

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

### -DSRecordGenerationAlgorithm
Specifies an array of cryptographic algorithms for domain service records.
The acceptable values for this parameter are:

- Sha1
- Sha256
- Sha384

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DSRecordSetTtl
Specifies a TTL time span for the set of domain service records.
The default value is the same as the TTL for the zone.

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

### -EnableRfc5011KeyRollover
Specifies whether a server uses RFC 5011 key rollover.

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

### -NSec3HashAlgorithm
Specifies an NSEC3 hash algorithm.
The only possible value is RsaSha1.

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

### -NSec3Iterations
Specifies a number of NSEC3 hash iterations to perform when it signs a DNS zone.
The default value is 50.

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NSec3OptOut
Specifies whether to sign the DNS zone by using NSEC opt-out.
The default value is $False.

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

### -NSec3RandomSaltLength
Specifies the length of a salt value.
The default length is 8.

```yaml
Type: Byte
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NSec3UserSalt
Specifies a user salt string.
The default value is Null or -.

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

### -ParentHasSecureDelegation
Specifies whether a parent has secure delegation for a zone.
The default value is $False.

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

### -PropagationTime
Specifies a propagation time as a time-span object.
This is the expected time required to propagate zone changes.

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

### -SecureDelegationPollingPeriod
Specifies a delegation polling period as a time-span object.
This is the time between polling attempts for key rollovers for child zones.
The default value is 12 hours.

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

### -SignatureInceptionOffset
Specifies the signature inception as a time-span object.
This value is how far in the past DNSSEC signature validity periods begin.
The default value is one hour.

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

### Microsoft.Management.Infrastructure.CimInstance#DnsServerDnsSecZoneSetting

## NOTES

## RELATED LINKS

[Get-DnsServerDnsSecZoneSetting](./Get-DnsServerDnsSecZoneSetting.md)

[Test-DnsServerDnsSecZoneSetting](./Test-DnsServerDnsSecZoneSetting.md)

