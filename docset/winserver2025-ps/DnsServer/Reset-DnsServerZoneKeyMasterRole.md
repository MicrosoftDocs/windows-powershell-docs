---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DnsServerZoneKeyMasterRole_v1.0.0.cdxml-help.xml
Module Name: DnsServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dnsserver/reset-dnsserverzonekeymasterrole?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Reset-DnsServerZoneKeyMasterRole
---

# Reset-DnsServerZoneKeyMasterRole

## SYNOPSIS
Transfers the role of Key Master for a DNS zone.

## SYNTAX

```
Reset-DnsServerZoneKeyMasterRole [-ZoneName] <String> [-Force] [[-KeyMasterServer] <String>] [-SeizeRole]
 [-PassThru] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Reset-DnsServerZoneKeyMasterRole** cmdlet transfers the role of DNS Security (DNSSEC) Key Master server.
Any authoritative Domain Name System (DNS) server that hosts a primary copy of the zone can be the Key Master server.

This cmdlet attempts to connect to the current Key Master server.
If it cannot connect to that server, the cmdlet does not make the change unless you specify **SeizeRole**.

This cmdlet prompts the user for confirmation before it transfers the role unless you use the **Force** switch.

## EXAMPLES

### Example 1: Transfer the role
```
PS C:\> Reset-DnsServerZoneKeyMasterRole -ZoneName "west01.contoso.com" -KeyMasterServer "root.contoso.com"
```

This command transfers the Key Master role for the zone named west01.contoso.com to the server named keys.contoso.com.
If the cmdlet cannot verify with the current Key Master server, it does not transfer the role.

### Example 2: Transfer the role, required
```
PS C:\> Reset-DnsServerZoneKeyMasterRole -ZoneName "west01.contoso.com" -KeyMasterServer "keys.contoso.com" -SeizeRole
```

This command transfers the Key Master role for the zone named west01.contoso.com to a server named keys.contoso.com.
If the cmdlet cannot verify with the current Key Master server, the cmdlet nevertheless transfers the role.

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
Transfers the role without prompting you for confirmation.
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

### -KeyMasterServer
Specifies the name of a DNS server.
Use a NetBIOS name, IP address, or fully qualified domain name.
The cmdlet makes this server the Key Master server for the specified zone.
The specified zone must be present on the DNS server as a primary zone.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
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

### -SeizeRole
Indicates that this cmdlet seizes the Key Master role.
Unless this switch is specified, the cmdlet does not make a change if it cannot reach the current Key Master server.

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
Specifies a name of a zone.
The cmdlet transfers the Key Master role for this zone.

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

### System.String

## NOTES

## RELATED LINKS

