---
external help file: DnsServer_Cmdlets.xml
Module Name: DnsServer
online version: https://docs.microsoft.com/powershell/module/dnsserver/import-dnsservertrustanchor?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Import-DnsServerTrustAnchor

## SYNOPSIS
Imports a trust anchor for a DNS server.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Import-DnsServerTrustAnchor [-KeySetFile] <String> [-AsJob] [-CimSession <CimSession[]>]
 [-ComputerName <String>] [-PassThru] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Import-DnsServerTrustAnchor [-AsJob] [-CimSession <CimSession[]>] [-ComputerName <String>] [-PassThru]
 [-ThrottleLimit <Int32>] -DSSetFile <String> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Import-DnsServerTrustAnchor** cmdlet imports a trust anchor from a specified file for a Domain Name System (DNS) server.
If you specify a key set file, the cmdlet imports the DNS public key (DNSKEY) record set from the input key set file.
This is the default parameter set.

If you specify a delegation signer (DS) set file, the cmdlet imports the DS record set from the input dsset file.
If no trust anchor exists, the cmdlet creates one before it imports a trust anchor.

## EXAMPLES

### Example 1: Import a trust anchor by using a key set file
```
PS C:\> Import-DnsServerTrustAnchor -KeySetFile "C:\Windows\System32\dns\keyset-west.contoso.com" -PassThru -Verbose
```

This command imports a trust anchor for the zone named west.contoso.com by using a specified key set file.

### Example 2: Import a trust record by using a DS set file
```
PS C:\>Import-DnsServerTrustAnchor -DSSetFile "C:\Windows\System32\dns\dsset-west.contoso.com" -PassThru -Verbose
```

This command imports a trust anchor (DS record) for the zone named west.contoso.com by using a specified DS set file.

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
You can specify The acceptable values for this parameter are: an IP address or any value that resolves to an IP address, such as a fully qualified domain name (FQDN), host name, or NETBIOS name.

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

### -DSSetFile
Specifies the path of a DS set file.

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

### -KeySetFile
Specifies the path of a key set file.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
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

### Microsoft.Management.Infrastructure.CimInstance#DnsServerTrustAnchor[]

## NOTES

## RELATED LINKS

[Add-DnsServerTrustAnchor](./Add-DnsServerTrustAnchor.md)

[Get-DnsServerTrustAnchor](./Get-DnsServerTrustAnchor.md)

[Remove-DnsServerTrustAnchor](./Remove-DnsServerTrustAnchor.md)

