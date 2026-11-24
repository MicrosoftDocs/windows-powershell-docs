---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DnsServerSigningKey_v1.0.0.cdxml-help.xml
Module Name: DnsServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dnsserver/add-dnsserversigningkey?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-DnsServerSigningKey
---

# Add-DnsServerSigningKey

## SYNOPSIS
Adds a KSK or ZSK to a signed zone.

## SYNTAX

```
Add-DnsServerSigningKey [-ZoneName] <String> [[-Type] <String>] [[-CryptoAlgorithm] <String>]
 [-ComputerName <String>] [[-KeyLength] <UInt32>] [-InitialRolloverOffset <TimeSpan>]
 [-DnsKeySignatureValidityPeriod <TimeSpan>] [-DSSignatureValidityPeriod <TimeSpan>]
 [-ZoneSignatureValidityPeriod <TimeSpan>] [-RolloverPeriod <TimeSpan>] [-ActiveKey <String>]
 [-StandbyKey <String>] [-NextKey <String>] [-KeyStorageProvider <String>] [-StoreKeysInAD <Boolean>]
 [-PassThru] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Add-DnsServerSigningKey** cmdlet adds a Key Signing Key (KSK) or Zone Signing Key (ZSK) key to a Domain Name System (DNS) signed zone.

## EXAMPLES

### Example 1: Add a KSK to a DNS zone
```
PS C:\> Add-DnsServerSigningKey -ZoneName "corp.contoso.com" -Type "KeySigningKey" -CryptoAlgorithm "RsaSha1NSec3" -KeyLength 2048 -PassThru -Verbose
```

This command adds a KSK to the DNS signed-zone corp.contoso.com.

## PARAMETERS

### -ActiveKey
Specifies a signing key pointer string for the KSK's active key.

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
Specifies a remote DNS server.
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

### -CryptoAlgorithm
Specifies a cryptographic algorithm to use for key generation.
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
Accepted values: RsaSha1, RsaSha256, RsaSha512, RsaSha1NSec3, ECDsaP256Sha256, ECDsaP384Sha384

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DSSignatureValidityPeriod
Specifies the amount of time that signatures that cover DS record sets are valid.

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

### -DnsKeySignatureValidityPeriod
Specifies the amount of time that signatures that cover DNSKEY record sets are valid.

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

### -InitialRolloverOffset
Specifies the amount of time to delay the first scheduled key rollover.
You can use **InitialRolloverOffset** to stagger key rollovers.

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

### -KeyLength
Specifies the bit length of a key.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -KeyStorageProvider
Specifies the Key Storage Provider that the DNS server uses to generate keys.

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

### -NextKey
Specifies a signing key pointer string for the next key.
The DNS server uses this key during the next key rollover event.

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

### -RolloverPeriod
Specifies the amount of time between scheduled key rollovers.

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

### -StandbyKey
Specifies a signing key pointer string for the KSK's standby key.

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

### -StoreKeysInAD
Specifies whether to store the keys in Active Directory Domain Services (AD DS).
This setting applies only to Active Directory-integrated zones when the vendor of KeyStorageProvider is Microsoft.

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

### -Type
Specifies whether a key is a KSK or a ZSK.

```yaml
Type: String
Parameter Sets: (All)
Aliases: KeyType
Accepted values: KeySigningKey, ZoneSigningKey

Required: False
Position: 2
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

### -ZoneName
Specifies the name of the zone in which DNS Security Extensions (DNSSEC) operations are performed.

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

### -ZoneSignatureValidityPeriod
Specifies the amount of time that signatures that cover all other record sets are valid.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#DnsServerSigningKey

## NOTES

## RELATED LINKS

[Disable-DnsServerSigningKeyRollover](./Disable-DnsServerSigningKeyRollover.md)

[Enable-DnsServerSigningKeyRollover](./Enable-DnsServerSigningKeyRollover.md)

[Get-DnsServerSigningKey](./Get-DnsServerSigningKey.md)

[Invoke-DnsServerSigningKeyRollover](./Invoke-DnsServerSigningKeyRollover.md)

[Remove-DnsServerSigningKey](./Remove-DnsServerSigningKey.md)

[Set-DnsServerSigningKey](./Set-DnsServerSigningKey.md)

