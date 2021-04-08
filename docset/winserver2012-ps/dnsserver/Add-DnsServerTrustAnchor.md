---
author: Kateyanne
external help file: DnsServer_Cmdlets.xml
manager: dansimp
Module Name: DnsServer
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/dnsserver/add-dnsservertrustanchor?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Add-DnsServerTrustAnchor

## SYNOPSIS
Adds a trust anchor to a DNS server.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Add-DnsServerTrustAnchor [-Name] <String> [-CryptoAlgorithm] <String> [-AsJob] [-CimSession <CimSession[]>]
 [-ComputerName <String>] [-KeyProtocol <String>] [-PassThru] [-ThrottleLimit <Int32>] -Base64Data <String>
 [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Add-DnsServerTrustAnchor [-Name] <String> [-CryptoAlgorithm] <String> [-AsJob] [-CimSession <CimSession[]>]
 [-ComputerName <String>] [-PassThru] [-ThrottleLimit <Int32>] -Digest <String> -DigestType <String>
 -KeyTag <UInt16> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Add-DnsServerTrustAnchor** cmdlet adds a trust anchor (DNSKEY record or DS record) to a DNS server.
If no trust anchor is present, the cmdlet creates one.
If you specify the **DigestType** parameter, the cmdlet adds a trust anchor delegation signer (DS) record.

## EXAMPLES

### Example 1: Add a trust anchor to a DNS server
```
PS C:\>Get-DnsServerResourceRecord -ZoneName "sec.contoso.com" -RRType "dnskey" -ComputerName DNS1 | %{ $_.RecordData | Add-DnsServerTrustAnchor -PassThru -Verbose -Name "sec.contoso.com"}
```

This command uses the Get-DnsServerResourceRecord cmdlet to obtain a DnsKey resource record from the DNS server DNS1 for the zone named sec.contoso.com.
The command then uses the pipe operator to send it to the Add-DnsServerTrustAnchor cmdlet to add a trust anchor to the current DNS server for this zone.

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

### -Base64Data
Specifies key data.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
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

### -ComputerName
Specifies a remote DNS server. 
The acceptable values for this parameter are: an IP address or any value that resolves to an IP address, such as a fully qualified domain name (FQDN), host name, or NETBIOS name.

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
Specifies the cryptographic algorithm that the cmdlet uses for key generation.

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

### -Digest
Specifies the DS digest data.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
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
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -KeyProtocol
Specifies the protocol name.
The default is DNSSEC.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

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
Parameter Sets: UNNAMED_PARAMETER_SET_2
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
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
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

### Microsoft.Management.Infrastructure.CimInstance#DnsServerTrustAnchor

## NOTES

## RELATED LINKS

[Get-DnsServerTrustAnchor](./Get-DnsServerTrustAnchor.md)

[Import-DnsServerTrustAnchor](./Import-DnsServerTrustAnchor.md)

[Remove-DnsServerTrustAnchor](./Remove-DnsServerTrustAnchor.md)

[Get-DnsServerResourceRecord](./Get-DnsServerResourceRecord.md)

