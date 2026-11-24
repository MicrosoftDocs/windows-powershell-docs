---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DnsServerDnsSecPublicKey_v1.0.0.cdxml-help.xml
Module Name: DnsServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dnsserver/export-dnsserverdnssecpublickey?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Export-DnsServerDnsSecPublicKey
---

# Export-DnsServerDnsSecPublicKey

## SYNOPSIS
Exports DS and DNSKEY information for a DNSSEC-signed zone.

## SYNTAX

### DnsKey (Default)
```
Export-DnsServerDnsSecPublicKey [-ComputerName <String>] [-ZoneName] <String> [-Path <String>] [-PassThru]
 [-UnAuthenticated] [-Force] [-NoClobber] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### DS
```
Export-DnsServerDnsSecPublicKey [-ComputerName <String>] [-ZoneName] <String> [-Path <String>] [-PassThru]
 [-UnAuthenticated] [-Force] [-NoClobber] -DigestType <String[]> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Export-DnsServerDnsSecPublicKey** cmdlet exports delegation signer (DS) or Domain Name System public key (DNSKEY) information for a Domain Name System Security Extensions (DNSSEC)-signed zone.

## EXAMPLES

### Example 1: Export a trust anchor to a file share
```
PS C:\> Export-DnsServerDnsSecPublicKey -ComputerName "DNSDC1.Contoso.com" -ZoneName "Contoso.com" -Path "\\MyDNSKeyShare\keys" -PassThru -DigestType "Sha1"

Exporting a trust anchor without using authentication is insecure unless DNSSEC is active on "${ComputerName}", a trust anchor covering "${ZoneName}" is installed, and the connection between the local machine and "${ComputerName}" is secure. Consider alternative means of exporting the trust anchors, such as the DNSCMD protocol, email, or HTTPS. Proceed? [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): Y
```

This command exports the trust anchor (DS record) for Contoso.com to a file share.
A DNS administrator runs this command from the DNS server that hosts the zone Contoso.com and specifies that the zone signing key uses the SHA-1 algorithm to create the DS record.

This command creates Dsset-Contoso.com in \\\\MyDNSKeyShare\keys and writes the DS record in the Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DNS/DNS/DnsServerResourceRecord format.

### Example 2: Export a trust anchor by using unauthorized access
```
PS C:\> Export-DnsServerDnsSecPublicKey -ComputerName "DNSDC1.contoso.com" -ZoneName "Contoso.com" - Path "\\MyDNSKeyShare\keys" -PassThru -UnAuthorized -Force

Exporting a trust anchor without using authentication is insecure unless DNSSEC is active on "${ComputerName}", a trust anchor covering "${ZoneName}" is installed, and the connection between the local machine and "${ComputerName}" is secure. Consider alternative means of exporting the trust anchors, such as the DNSCMD protocol, email, or HTTPS. Proceed? [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): Y
Note: User typing N exits out of the command with no export or output
```

This command exports a trust anchor (DNSKEY record) for Contoso.com to a file share.
The DNS administrator who runs this command has no permissions to the DNS server that hosts the zone Contoso.com.
This command specifies that the zone signing key uses the SHA-1 algorithm to create the DS record.

This command creates Keyset-Contoso.com in \\\\MyDNSKeyShare\keys and writes the DS record in the Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DNS/DNS/DnsServerResourceRecord format.

### Example 3: Get the trust anchors for all the signed zones
```
PS C:\> Get-DnsServerZone | ForEach-Object {Export-DnsServerDnsSecPublicKey -ComputerName "DNSDC1.Contoso.com" -ZoneName "Contoso.com" -Path "\\MyDNSKeyShare\keys" -PassThru -UnAuthorized -Force  }
```

This command gets the trust anchors for all the signed zones that are hosted on the DNS server Contoso.com.
In this scenario the DNS Server is currently hosting signed zones for contoso.com, dinnernow.com and hrweb.net

The command uses a **ForEach-Object** cmdlet to export the trust anchors and pass the results to the **Get-DnsServerZone** cmdlet by using the pipeline operator.

This command creates a keyset file in the share for each signed zone that is hosted on the DNS server (Keyset-Contoso.com, Keyset-Dinnernow.com, Keyset-Hrweb.net) and writes the DNSKEY record in the Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DNS/DNS/DnsServerResourceRecord format.

### Example 4: Import a trust anchor to a non-authorized DN server
```
PS C:\> $publicKey = Export-DnsServerDnssecPublicKey -ZoneName "contoso.com" -Path "C:\" -PassThru -UnAuthenticated -Force
PS C:\> $publicKey[0].RecordData | Add-DnsServerTrustAnchor -Name "constoso.com" -ComputerName "DNSDC1.Contoso.com"
```

The first command exports the trust anchor (DNSKEY record) for Contoso.com to the specified path, and stores the results in the **$publicKey** variable.
The *UnAuthenticated* parameter indicates that the DNS administrator who runs this command has no permissions to the DNS server that hosts the zone Contoso.com.

The second command adds the first trust record that was exported from Contoso.com into a non-authoritative DNS server named DNSDC1.Contoso.com.

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

### -DigestType
Specifies an array of algorithms that the zone signing key uses to create the DS record.
The acceptable values for this parameter are:
- Sha1
- Sha256
- Sha384

```yaml
Type: String[]
Parameter Sets: DS
Aliases:
Accepted values: Sha1, Sha256, Sha384

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Force
Exports the signing key without prompting you for confirmation.
By default, the cmdlet prompts you for confirmation before it proceeds.

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

### -NoClobber
Specifies that the export operation does not overwrite an existing export file that has the same name.

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

### -Path
Specifies the absolute path that the cmdlet uses to place the keyset file.
The cmdlet automatically names the file according to the zone name.

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

### -UnAuthenticated
Indicates that an unauthenticated user is running this cmdlet.
The provider DNS server queries for the DS or DNSKEY information and exports the required data even if you do not have permissions to run the cmdlet on the remote DNS server.

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
Specifies the name of the primary zone for which the cmdlet exports the signing keys.

```yaml
Type: String
Parameter Sets: (All)
Aliases: TrustPointName, TrustAnchorName

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

### Microsoft.Management.Infrastructure.CimInstance#DnsServerResourceRecord

## NOTES

## RELATED LINKS

[Add-DnsServerTrustAnchor](./Add-DnsServerTrustAnchor.md)

[Get-DnsServerZone](./Get-DnsServerZone.md)

