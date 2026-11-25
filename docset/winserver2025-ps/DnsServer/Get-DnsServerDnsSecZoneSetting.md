---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DnsServerDnsSecZoneSetting_v1.0.0.cdxml-help.xml
Module Name: DnsServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dnsserver/get-dnsserverdnsseczonesetting?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DnsServerDnsSecZoneSetting
---

# Get-DnsServerDnsSecZoneSetting

## SYNOPSIS
Gets DNSSEC settings for a zone.

## SYNTAX

### DnsSecSetting (Default)
```
Get-DnsServerDnsSecZoneSetting [-ZoneName] <String[]> [-ComputerName <String>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### SigningMetadata
```
Get-DnsServerDnsSecZoneSetting [-ZoneName] <String[]> [-ComputerName <String>] [-SigningMetadata]
 [-IncludeKSKMetadata] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-DnsServerDnsSecZoneSetting** cmdlet gets the Domain Name System Security Extensions (DNSSEC) settings for a zone on a Domain Name System (DNS) server.

If you specify the *SigningMetaData* parameter, the cmdlet outputs a signing metadata object that contains all the configuration information about the zone signing.
You can use this object to import the configuration for zone signing to another server by using the **Set-DnsServerDnsSecZoneSetting** cmdlet.

## EXAMPLES

### Example 1: Get DNSSEC settings
```
PS C:\> Get-DnsServerDnsSecZoneSetting -ZoneName "western.contoso.com"
ZoneName                      : western.contoso.com
IsKeyMasterServer             : True
KeyMasterServer               : root
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
EnableRfc5011KeyRollover      : False
ParentHasSecureDelegation     : False
SecureDelegationPollingPeriod : 12:00:00
PropagationTime               : 00:00:00
SignatureInceptionOffset      : 01:00:00
```

This command gets the DNS Security Extensions for the zone named western.contoso.com.

### Example 2: Get DNSSEC setting with signing metadata
```
PS C:\> Get-DnsServerDnsSecZoneSetting -SigningMetadata -ZoneName western.contoso.com
DnsSecResourceRecords         : {DnsServerResourceRecord, DnsServerResourceRecord, DnsServerResourceRecord, DnsServerResourceRecord...}
DnsSecZoneSetting             : DnsServerDnsSecZoneSetting
KeyExtendedInformation        : {DnsServerSigningKeyExtendedInformation}
PSComputerName                :
ZoneName                      : western.contoso.com
IsSigned                      : True
DenialOfExistence             : NSec3
NSec3HashAlgorithm            : RsaSha1
NSec3Iterations               : 50
NSec3OptOut                   : False
NSec3RandomSaltLength         : 8
NSec3UserSalt                 : -
DistributeTrustAnchor         : None
EnableRfc5011KeyRollover      : True
DSRecordGenerationAlgorithm   : {Sha1, Sha256}
DSRecordSetTtl                : 01:00:00
DnsKeyRecordSetTtl            : 01:00:00
SignatureInceptionOffset      : 01:00:00
SecureDelegationPollingPeriod : 12:00:00
PropagationTime               : 00:00:00
ParentHasSecureDelegation     : False
NSec3CurrentSalt              : 64A9522428558341
CurrentRollingSkdGuid         : 92491d13-f777-4d48-a9b6-6625cfd5cb9e
```

This command gets the DNS Security Extensions signing metadata for the zone named western.contoso.com.
The metadata returned can be imported on a non-key master server to begin signing with enhanced key management for file-backed zones.

### Example 3: Get DNSSEC settings with signing metadata and key signing key information
```
PS C:\> Get-DnsServerDnsSecZoneSetting -SigningMetadata -ZoneName "western.contoso.com" -IncludeKSKMetadata
DnsSecResourceRecords         : {DnsServerResourceRecord, DnsServerResourceRecord, DnsServerResourceRecord, DnsServerResourceRecord...}
DnsSecZoneSetting             : DnsServerDnsSecZoneSetting
KeyExtendedInformation        : {DnsServerSigningKeyExtendedInformation, DnsServerSigningKeyExtendedInformation}
PSComputerName                :
ZoneName                      : western.contoso.com
IsSigned                      : True
DenialOfExistence             : NSec3
NSec3HashAlgorithm            : RsaSha1
NSec3Iterations               : 50
NSec3OptOut                   : False
NSec3RandomSaltLength         : 8
NSec3UserSalt                 : -
DistributeTrustAnchor         : None
EnableRfc5011KeyRollover      : True
DSRecordGenerationAlgorithm   : {Sha1, Sha256}
DSRecordSetTtl                : 01:00:00
DnsKeyRecordSetTtl            : 01:00:00
SignatureInceptionOffset      : 01:00:00
SecureDelegationPollingPeriod : 12:00:00
PropagationTime               : 00:00:00
ParentHasSecureDelegation     : False
NSec3CurrentSalt              : 64A9522428558341
CurrentRollingSkdGuid         : 92491d13-f777-4d48-a9b6-6625cfd5cb9e
```

This command gets the DNS Security Extensions signing metadata and key signing key information for the zone named western.contoso.com.
The metadata returned can be imported on a non-key master server to begin signing with enhanced key management for file-backed zones.

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

### -IncludeKSKMetadata
Indicates that the cmdlet includes KSK metadata in the output object.
You can import the output object that contains the KSK metadata on another server.
If the server that imports the input object requires the Key Master role, the server can seize the Key Master role.
If the output object does not contain the KSK metadata, the server that imports the output object cannot seize the key Master Role while retaining the existing keys, and you must resign the whole zone with new keys.

```yaml
Type: SwitchParameter
Parameter Sets: SigningMetadata
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SigningMetadata
Indicates that the cmdlet includes all signing metadata in the output object.

```yaml
Type: SwitchParameter
Parameter Sets: SigningMetadata
Aliases:

Required: True
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

### -ZoneName
Specifies an array of names of DNS zones.

```yaml
Type: String[]
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

### Microsoft.Management.Infrastructure.CimInstance#DnsServerDnsSecZoneSetting[]
The **DnsServerDnsSecZoneSetting** object contains the following fields:

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

If you specify the *SigningMetadata* parameter, the object returned is of type DnsServerZoneSigningMetadata
{

- DnsServerDnsSecZoneSetting DnsSecZoneSetting
- DnsServerSigningKeyExtendedInformation \[\] KeyExtendedInformation
- DnsServerResourceRecord\[\] DnsSecRecords

}

DnsServerDnsSecZoneSetting
{

- String ZoneName
- Bool DenialOfExistence
- Bool NSec3HashAlgorithm
- Integer NSec3Iterations
- Bool NSec3OptOut
- Integer NSec3RandomSaltLength
- String NSec3UserSalt
- String\[\] DistributeTrustAnchor
- Bool EnableRfc5011KeyRollover
- String\[\] DSRecordGenerationAlgorithm
- Bool ParentHasSecureDelegation
- DateTime DsRecordSetTtl
- DateTime DnsKeyRecordSetTtl
- DateTime SignatureInceptionOffset
- DateTime SecureDelegationPollingPeriod
- DateTime PropagationTime
- Bool IsKeyMasterServer
- String KeyMasterServer
- String KeyMasterStatus
- Bool IsSigned
- String NSec3CurrentSalt
- String CurrentRollingSkdGuid

}

DnsServerSigningKeyOpState
{

- Integer CurrentRolloverState
- Bool ManualTrigger
- Integer PreRollEventFired
- TimeSpan NextKeyGenerationTime
- DnsServerResourceRecordDnsKey\[\] RevokedOrSwappedDnsKeys
- DnsServerResourceRecordDnsKey\[\] FinalDnsKeys
- Integer ActiveKeyScope
- Integer StandbyKeyScope
- Integer NextKeyScope

}

DnsServerSigningKeyExtendedInformation
{

- DnsServerSigningKey SigningKey
- DnsServerSigningKeyOpState SigningKeyOpState
}

## NOTES

## RELATED LINKS

[Set-DnsServerDnsSecZoneSetting](./Set-DnsServerDnsSecZoneSetting.md)

[Test-DnsServerDnsSecZoneSetting](./Test-DnsServerDnsSecZoneSetting.md)

