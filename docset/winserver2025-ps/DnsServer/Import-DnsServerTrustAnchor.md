---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DnsServerTrustAnchor_v1.0.0.cdxml-help.xml
Module Name: DnsServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dnsserver/import-dnsservertrustanchor?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Import-DnsServerTrustAnchor
---

# Import-DnsServerTrustAnchor

## SYNOPSIS
Imports a trust anchor for a DNS server.

## SYNTAX

### KeySet (Default)
```
Import-DnsServerTrustAnchor [-ComputerName <String>] [-PassThru] [-KeySetFile] <String>
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### DSSet
```
Import-DnsServerTrustAnchor [-ComputerName <String>] -DSSetFile <String> [-PassThru]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
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
PS C:\> Import-DnsServerTrustAnchor -DSSetFile "C:\Windows\System32\dns\dsset-west.contoso.com" -PassThru -Verbose
```

This command imports a trust anchor (DS record) for the zone named west.contoso.com by using a specified DS set file.

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
Specify the IP address or any value that resolves to an IP address, such as a fully qualified domain name (FQDN), host name, or NETBIOS name, for the DNS server.

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

### -DSSetFile
Specifies the path of a DS set file.

```yaml
Type: String
Parameter Sets: DSSet
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
Parameter Sets: KeySet
Aliases:

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

### Microsoft.Management.Infrastructure.CimInstance#DnsServerTrustAnchor[]

## NOTES

## RELATED LINKS

[Add-DnsServerTrustAnchor](./Add-DnsServerTrustAnchor.md)

[Get-DnsServerTrustAnchor](./Get-DnsServerTrustAnchor.md)

[Remove-DnsServerTrustAnchor](./Remove-DnsServerTrustAnchor.md)

