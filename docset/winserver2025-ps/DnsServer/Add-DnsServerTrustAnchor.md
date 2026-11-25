---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DnsServerTrustAnchor_v1.0.0.cdxml-help.xml
Module Name: DnsServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dnsserver/add-dnsservertrustanchor?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-DnsServerTrustAnchor
---

# Add-DnsServerTrustAnchor

## SYNOPSIS
Adds a trust anchor to a DNS server.

## SYNTAX

### DnsKey (Default)
```
Add-DnsServerTrustAnchor [-Name] <String> [-KeyProtocol <String>] -Base64Data <String> [-ComputerName <String>]
 [-CryptoAlgorithm] <String> [-PassThru] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### DS
```
Add-DnsServerTrustAnchor [-Name] <String> [-ComputerName <String>] [-CryptoAlgorithm] <String> [-PassThru]
 -KeyTag <UInt16> -DigestType <String> -Digest <String> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Root
```
Add-DnsServerTrustAnchor [-ComputerName <String>] [-PassThru] [-Root] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-DnsServerTrustAnchor** cmdlet adds a trust anchor (DNSKEY record or DS record) to a Domain Name System (DNS) server.
If no trust anchor is present, the cmdlet creates one.
If you specify the *DigestType* parameter, the cmdlet adds a trust anchor delegation signer (DS) record.

If you specify the *Root* parameter the cmdlet retrieves the trust anchors from the URL specified in RootTrustAnchorsURL property of the DNS server.

## EXAMPLES

### Example 1: Add a trust anchor to a DNS server
```
PS C:\> Get-DnsServerResourceRecord -ZoneName "sec.contoso.com" -RRType "dnskey" -ComputerName DNS1 | %{ $_.RecordData | Add-DnsServerTrustAnchor -PassThru -Verbose -Name "sec.contoso.com"}
VERBOSE: Adding trust anchor for trust point sec.contoso.com of type DNSKEY on server Server01.
TrustAnchorName             TrustAnchorType      TrustAnchorState     TrustAnchorData
---------------              ---------------      ----------------     ---------------
sec.contoso.com             DNSKEY               Valid                [23600][DnsSec][RsaSha256][AwEAAbZvBTiMzoqK...
VERBOSE: Adding trust anchor for trust point sec.contoso.com of type DNSKEY on server Server01.
sec.contoso.com             DNSKEY               Valid                [53180][DnsSec][RsaSha256][AwEAAbsS7NnziyRY...
VERBOSE: Adding trust anchor for trust point sec.contoso.com of type DNSKEY on server Server01.

sec.contoso.com             DNSKEY               Valid                [50272][DnsSec][RsaSha256][AwEAAe1EkxNj6M1b...
VERBOSE: Adding trust anchor for trust point sec.contoso.com of type DNSKEY on server Server01.
sec.contoso.com             DNSKEY               Valid                [37436][DnsSec][RsaSha256][AwEAAa1PJyk2lITB...
VERBOSE: Adding trust anchor for trust point sec.contoso.com of type DNSKEY on server Server01.
sec.contoso.com             DNSKEY               Valid                [2895][DnsSec][RsaSha1NSec3][AwEAAbOk5nl41M...
VERBOSE: Adding trust anchor for trust point sec.contoso.com of type DNSKEY on server Server01.
sec.contoso.com             DNSKEY               Valid                [62250][DnsSec][RsaSha1NSec3][AwEAAci9Ayfjg...
VERBOSE: Adding trust anchor for trust point sec.contoso.com of type DNSKEY on server Server01.
sec.contoso.com             DNSKEY               Valid                [47244][DnsSec][RsaSha1NSec3][AwEAAcFv94ne6...
```

This command uses the **Get-DnsServerResourceRecord** cmdlet to obtain a DnsKey resource record from the DNS server DNS1 for the zone named sec.contoso.com.
The command then uses the pipeline operator to send it to the **Add-DnsServerTrustAnchor** cmdlet to add a trust anchor to the current DNS server for this zone.

### Example 2: Add a trust anchor from the RootTrustAnchorsURL property
```
PS C:\> Add-DnsServerTrustAnchor -Root
```

This command adds the trust anchors from the URL specified by the **RootTrustAnchorsURL** property of the DNS server.

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

### -Base64Data
Specifies key data.

```yaml
Type: String
Parameter Sets: DnsKey
Aliases:

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
Specifies a remote DNS server.
The acceptable values for this parameter are:an IP address or any value that resolves to an IP address, such as a fully qualified domain name (FQDN), host name, or NETBIOS name.

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
Specifies the cryptographic algorithm that the cmdlet uses for key generation.
The acceptable values for this parameter are:

- RsaSha1
- RsaSha256
- RsaSha512
- RsaSha1NSec3
- ECDsaP256Sha256
- ECDsaP384Sha384

```yaml
Type: String
Parameter Sets: DnsKey, DS
Aliases:
Accepted values: RsaSha1, RsaSha256, RsaSha512, RsaSha1NSec3, ECDsaP256Sha256, ECDsaP384Sha384

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Digest
Specifies the DS digest data.

```yaml
Type: String
Parameter Sets: DS
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DigestType
Specifies the type of algorithm that the zone signing key uses to create the DS record.
Valid values are one or more of the following:
- Sha1
- Sha256
- Sha384

```yaml
Type: String
Parameter Sets: DS
Aliases:
Accepted values: Sha1, Sha256, Sha384

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -KeyProtocol
Specifies the key protocol.
The default is Dnssec.

```yaml
Type: String
Parameter Sets: DnsKey
Aliases:
Accepted values: DnsSec

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -KeyTag
Specifies the unique key tag that the DNS server uses to identify a key.

```yaml
Type: UInt16
Parameter Sets: DS
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of a trust anchor on a DNS server.

```yaml
Type: String
Parameter Sets: DnsKey, DS
Aliases: TrustAnchorName

Required: True
Position: 1
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

### -Root
Indicates that the cmdlet adds the trust anchor of the root zone from the URL specified by the **RootTrustAnchorsURL** property of the DNS server.

```yaml
Type: SwitchParameter
Parameter Sets: Root
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#DnsServerTrustAnchor
The DnsServerTrustAnchor object contains the following fields:

- EnteredStateTime
- KeyTag
- NextStateTime
- TrustAnchorData
- TrustAnchorName
- TrustAnchorState
- TrustAnchorType

## NOTES

## RELATED LINKS

[Get-DnsServerTrustAnchor](./Get-DnsServerTrustAnchor.md)

[Import-DnsServerTrustAnchor](./Import-DnsServerTrustAnchor.md)

[Remove-DnsServerTrustAnchor](./Remove-DnsServerTrustAnchor.md)

[Get-DnsServerResourceRecord](./Get-DnsServerResourceRecord.md)

