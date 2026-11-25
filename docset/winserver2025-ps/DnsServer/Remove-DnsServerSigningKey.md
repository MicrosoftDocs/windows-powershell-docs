---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DnsServerSigningKey_v1.0.0.cdxml-help.xml
Module Name: DnsServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dnsserver/remove-dnsserversigningkey?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-DnsServerSigningKey
---

# Remove-DnsServerSigningKey

## SYNOPSIS
Removes signing keys.

## SYNTAX

```
Remove-DnsServerSigningKey [-ZoneName] <String> [-PassThru] [-KeyId] <Guid[]> [-Force] [-ComputerName <String>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-DnsServerSigningKey** cmdlet removes one or more signing keys from the specified Domain Name System (DNS) zone.
This cmdlet removes signing keys on an unsigned zone that you incorrectly configured.
This cmdlet cannot remove active signing keys from a signed zone.

## EXAMPLES

### Example 1: Remove signing keys for a zone
```
PS C:\> Get-DnsServerSigningKey -ZoneName "west.contoso.com" | Remove-DnsServerSigningKey
```

This first part of the command gets the DNS server signing keys for the west.contoso.com zone and passes the results to the **Remove-DnsServerSigningKey** cmdlet by using the pipeline operator.
The second part of the command removes DNS server signing keys.

### Example 2: Remove a single signing key for a zone
```
PS C:\> Remove-DnsServerSigningKey -ZoneName contoso.com -KeyId "6ff2c4b3-3eeb-4074-908f-bca0cca153c7"
```

This command removes the signing key that has the ID 6ff2c4b3-3eeb-4074-908f-bca0cca153c7 from the zone named contoso.com.

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

### -Force
Removes the signing keys without prompting you for confirmation.
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

### -KeyId
Specifies an array of key identifiers.

```yaml
Type: Guid[]
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#DnsServerSigningKey[]

## NOTES

## RELATED LINKS

[Add-DnsServerSigningKey](./Add-DnsServerSigningKey.md)

[Disable-DnsServerSigningKeyRollover](./Disable-DnsServerSigningKeyRollover.md)

[Enable-DnsServerSigningKeyRollover](./Enable-DnsServerSigningKeyRollover.md)

[Get-DnsServerSigningKey](./Get-DnsServerSigningKey.md)

[Invoke-DnsServerSigningKeyRollover](./Invoke-DnsServerSigningKeyRollover.md)

[Set-DnsServerSigningKey](./Set-DnsServerSigningKey.md)

