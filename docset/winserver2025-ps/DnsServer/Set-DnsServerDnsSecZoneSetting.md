---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DnsServerDnsSecZoneSetting_v1.0.0.cdxml-help.xml
Module Name: DnsServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dnsserver/set-dnsserverdnsseczonesetting?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-DnsServerDnsSecZoneSetting
---

# Set-DnsServerDnsSecZoneSetting

## SYNOPSIS
Changes settings for DNSSEC for a zone.

## SYNTAX

### DnsSecSetting (Default)
```
Set-DnsServerDnsSecZoneSetting [-ZoneName] <String> [[-DenialOfExistence] <String>]
 [-NSec3HashAlgorithm <String>] [-NSec3Iterations <UInt16>] [-NSec3OptOut <Boolean>]
 [-NSec3RandomSaltLength <Byte>] [-NSec3UserSalt <String>] [-DistributeTrustAnchor <String[]>]
 [-EnableRfc5011KeyRollover <Boolean>] [-DSRecordGenerationAlgorithm <String[]>] [-DSRecordSetTtl <TimeSpan>]
 [-DnsKeyRecordSetTtl <TimeSpan>] [-SignatureInceptionOffset <TimeSpan>]
 [-SecureDelegationPollingPeriod <TimeSpan>] [-PropagationTime <TimeSpan>]
 [-ParentHasSecureDelegation <Boolean>] [-ComputerName <String>] [-PassThru] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SigningMetadata
```
Set-DnsServerDnsSecZoneSetting [-ZoneName] <String> [-ComputerName <String>] [-PassThru]
 [[-InputObject] <CimInstance>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-DnsServerDnsSecZoneSetting** cmdlet changes Domain Name System Security Extensions (DNSSEC) settings for the specified zone on a Domain Name System (DNS) server.

You can select which version of Next Secure (NSEC) to use to provide authenticated denial of existence.
Set the *DenialOfExistence* parameter to NSec or NSec3.
If you use NSec3, you can use either random salt or user-defined salt.

When using the *SigningMetadata* parameter set, the cmdlet takes **CimInstance#DnsServerZoneSigningMetadata** as an input object.
You can use this cmdlet with Get-DnsServerDnsSecZoneSetting to import the DNSSEC metadata of a zone from one DNS server to another DNS server.

## EXAMPLES

### Example 1: Modify RFC 5011 settings
```
PS C:\> Set-DnsServerDnsSecZoneSetting -ZoneName "west01.contoso.com" -EnableRfc5011KeyRollover $True -PassThru -Verbose

VERBOSE: Modifies the DNSSEC properties for the zone west01.contoso.com on server Server01.
VERBOSE: RFC5011KeyRollovers successfully set on server Server01.
ZoneName                      : west01.contoso.com
IsKeyMasterServer             : True
KeyMasterServer               : Server01.west01.contoso.com
KeyMasterStatus               : Online
DenialOfExistence             : NSec3
NSec3HashAlgorithm            : RsaSha1
NSec3Iterations               : 50
NSec3OptOut                   : False
IsNSec3SaltConfigured         : True
NSec3RandomSaltLength         : 8
NSec3UserSalt                 : -
DnsKeyRecordSetTTL            : 01:00:00
DSRecordSetTTL                : 01:00:00
DSRecordGenerationAlgorithm   : {Sha1, Sha256}
DistributeTrustAnchor         : {None}
EnableRfc5011KeyRollover      : True
ParentHasSecureDelegation     : False
SecureDelegationPollingPeriod : 12:00:00
PropagationTime               : 2.00:00:00
SignatureInceptionOffset      : 01:00:00
```

This command modifies RFC 5011 settings for a zone named west01.contoso.com.
The example uses the *PassThru* parameter to produce output and the *Verbose* parameter to include all output.

### Example 2: Import DNSSEC signing metadata
```
PS C:\> Get-DnsServerDnsSecZoneSetting -SigningMetadata -ZoneName "contoso.com" -IncludeKSKMetadata -ComputerName "KeyMaster01" | Set-DnsServerDnsSecZoneSetting -ComputerName "EdgeServer01"
```

This command uses the **Get-DnsServerDnsSecZoneSetting** cmdlet to get the DNSSEC signing metadata, that includes KSK metadata, from the DNS server named KeyMaster01 in the zone named contoso.com.
The command passes the DNSSEC signing metadata to the current cmdlet by using the pipeline operator.
The command sets the DNSSEC signing metadata on the non-key master primary server named EdgeServer01.
If the zone on the server is not already signed, the command initiates signing on the server by using zone signing keys.

## PARAMETERS

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

### -DSRecordGenerationAlgorithm
Specifies an array of cryptographic algorithms for domain service records.
The acceptable values for this parameter are:

- Sha1
- Sha256
- Sha384

```yaml
Type: String[]
Parameter Sets: DnsSecSetting
Aliases:
Accepted values: None, Sha1, Sha256, Sha384

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
Parameter Sets: DnsSecSetting
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Parameter Sets: DnsSecSetting
Aliases:
Accepted values: NSec, NSec3

Required: False
Position: 2
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
Parameter Sets: DnsSecSetting
Aliases:
Accepted values: None, DnsKey

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
Parameter Sets: DnsSecSetting
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
Parameter Sets: DnsSecSetting
Aliases:

Required: False
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
Parameter Sets: SigningMetadata
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -NSec3HashAlgorithm
Specifies an NSEC3 hash algorithm.
The only possible value is RsaSha1.

```yaml
Type: String
Parameter Sets: DnsSecSetting
Aliases:
Accepted values: RsaSha1

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
Parameter Sets: DnsSecSetting
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
Parameter Sets: DnsSecSetting
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
Parameter Sets: DnsSecSetting
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
Parameter Sets: DnsSecSetting
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
Parameter Sets: DnsSecSetting
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
The default value is 2 days.

```yaml
Type: TimeSpan
Parameter Sets: DnsSecSetting
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
Parameter Sets: DnsSecSetting
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
Parameter Sets: DnsSecSetting
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#DnsServerDnsSecZoneSetting
The DnsServerDnsSecZoneSetting object contains the following fields:

- DenialOfExistence
- DistributeTrustAnchor
- DnsKeyRecordSetTtl
- DSRecordGenerationAlgorithm
- DSRecordSetTtl
- EnableRfc5011KeyRollover
- IsKeyMasterServer
- KeyMasterServer
- KeyMasterStatus
- NSec3HashAlgorithm
- NSec3Iterations
- NSec3OptOut
- NSec3RandomSaltLength
- NSec3UserSalt
- ParentHasSecureDelegation
- PropagationTime
- SecureDelegationPollingPeriod
- SignatureInceptionOffset
- ZoneName

## NOTES

## RELATED LINKS

[Get-DnsServerDnsSecZoneSetting](./Get-DnsServerDnsSecZoneSetting.md)

[Test-DnsServerDnsSecZoneSetting](./Test-DnsServerDnsSecZoneSetting.md)

