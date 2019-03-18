---
external help file: DnsServer_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: E3C5714A-FF61-4485-9F86-D49A3AC8A86E
ms.reviewer:
ms.author: kenwith
author: kenwith
---

# Export-DnsServerDnsSecPublicKey

## SYNOPSIS
Exports DS and DNSKEY information for a DNSSEC-signed zone.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Export-DnsServerDnsSecPublicKey [-ZoneName] <String> [-AsJob] [-CimSession <CimSession[]>]
 [-ComputerName <String>] [-Force] [-NoClobber] [-PassThru] [-Path <String>] [-ThrottleLimit <Int32>]
 [-UnAuthenticated] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Export-DnsServerDnsSecPublicKey [-ZoneName] <String> [-AsJob] [-CimSession <CimSession[]>]
 [-ComputerName <String>] [-Force] [-NoClobber] [-PassThru] [-Path <String>] [-ThrottleLimit <Int32>]
 [-UnAuthenticated] -DigestType <String[]> [-Confirm] [-WhatIf]
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

This command creates Keyset-Contoso.com in \\\\MyDNSKeyShare\keys and writes the DS record in the Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DNS/DNS/DnsServerResourceRecord format.

### Example 2: Export a trust anchor by using unauthorized access
```
PS C:\>Export-DnsServerDnsSecPublicKey -ComputerName "DNSDC1.contoso.com" -ZoneName "Contoso.com" - Path "\\MyDNSKeyShare\keys" -PassThru -UnAuthorized -Force -DigestType "Sha1"
Exporting a trust anchor without using authentication is insecure unless DNSSEC is active on "${ComputerName}", a trust anchor covering "${ZoneName}" is installed, and the connection between the local machine and "${ComputerName}" is secure. Consider alternative means of exporting the trust anchors, such as the DNSCMD protocol, email, or HTTPS. Proceed? [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): Y
Note: User typing N exits out of the command with no export or output
```

This command exports a trust anchor (DNSKEY record) for Contoso.com to a file share.
The DNS administrator who runs this command has no permissions to the DNS server that hosts the zone Contoso.com.
This command specifies that the zone signing key uses the SHA-1 algorithm to create the DS record.

This command creates Keyset-Contoso.com in \\\\MyDNSKeyShare\keys and writes the DS record in the Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DNS/DNS/DnsServerResourceRecord format.

### Example 3: Get the trust anchors for all the signed zones
```
PS C:\>Get-DnsServerZone | ForEach-Object {Export-DnsServerDnsSecPublicKey -ComputerName "DNSDC1.Contoso.com" -ZoneName "Contoso.com" -Path "\\MyDNSKeyShare\keys" -PassThru -UnAuthorized -Force  }
```

This command gets the trust anchors for all the signed zones that are hosted on the DNS server Contoso.com.
In this scenario the DNS Server is currently hosting signed zones for contoso.com, dinnernow.com and hrweb.net

The command uses a Foreach-Object cmdlet to export the trust anchors and pipe the results to the **Get-DnsServerZone** cmdlet.

This command creates a keyset file in the share for each signed zone that is hosted on the DNS server (Keyset-Contoso.com, Keyset-Dinnernow.com, Keyset-Hrweb.net) and writes the DNSKEY record in the Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DNS/DNS/DnsServerResourceRecord format.

### Example 4: Import a trust anchor to a non-authorized DN server
```
PS C:\>$publicKey = Export-DnsServerDnssecPublicKey -ZoneName "contoso.com" -Path "C:\" -PassThru -UnAuthenticated -Force PS C:\>$publicKey[0].RecordData | Add-DnsServerTrustAnchor -Name "constoso.com" -ComputerName "DNSDC1.Contoso.com"
```

The first command exports the trust anchor (DNSKEY record) for Contoso.com to the specified path, and stores the results in the **$publicKey** variable.
The **UnAuthenticated** parameter indicates that the DNS administrator who runs this command has no permissions to the DNS server that hosts the zone Contoso.com.

The second command adds the first trust record that was exported from Contoso.com into a non-authoritative DNS server named DNSDC1.Contoso.com.

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
Specifies a remote DNS server.
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

### -DigestType
Specifies an array of algorithms that the zone signing key uses to create the DS record.
The acceptable values for this parameter are:
- Sha1
- Sha256
- Sha384

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

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
Specifies that an unauthenticated user is running this cmdlet.
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

### -ZoneName
Specifies the name of the primary zone for which the cmdlet exports the signing keys.

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

[Add-DnsServerTrustAnchor](./Add-DnsServerTrustAnchor.md)

[Get-DnsServerZone](./Get-DnsServerZone.md)

