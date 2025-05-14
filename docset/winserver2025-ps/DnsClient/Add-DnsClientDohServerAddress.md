---
description: The Add-DnsClientDohServerAddress cmdlet adds a DNS-over-HTTPS (DoH) server configuration to the supported DoH servers.
external help file: MSFT_DnsClientDohServerAddress.cdxml-help.xml
Module Name: DnsClient
ms.date: 08/31/2021
online version: https://learn.microsoft.com/powershell/module/dnsclient/add-dnsclientdohserveraddress?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-DnsClientDohServerAddress
---

# Add-DnsClientDohServerAddress

## SYNOPSIS
Adds a DoH server configuration to the supported DoH servers.

## SYNTAX

```
Add-DnsClientDohServerAddress [-ServerAddress] <String> [[-DohTemplate] <String>]
 [[-AllowFallbackToUdp] <Boolean>] [[-AutoUpgrade] <Boolean>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-DnsClientDohServerAddress** cmdlet adds a DNS-over-HTTPS (DoH) server configuration to the supported DoH servers.

## EXAMPLES

### Example 1: Add a DoH server
```powershell
Add-DnsClientDohServerAddress -ServerAddress 10.23.1.1 -DohTemplate https://adatum.com/dns-query
```

This example adds 10.23.1.1 to the system DoH list with the specified URI template.

### Example 2: Add a DoH server with automatic upgrade
```powershell
Add-DnsClientDohServerAddress -ServerAddress 10.23.1.1 -DohTemplate https://adatum.com/dns-query -AllowFallbackToUdp $True -AutoUpgrade $True
```

This example adds 10.23.1.1 to the system DoH list with the specified URI template.
The command upgrades any resolutions to 10.23.1.1 to DoH.
If the encrypted name resolution fails, the command allows fallback to unencrypted DNS.

## PARAMETERS

### -AllowFallbackToUdp
Specifies whether to allow fallback to unencrypted DNS if the DoH query to the server fails.
This parameter applies only if **AutoUpgrade** is `True`.
The default is `False`.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -AutoUpgrade
Specifies whether to encrypt all name resolutions to this server using the DoH settings.
The upgrade occurs if the server is configured on an adapter or if it is part of a Name Resolution Policy Table (NRPT) rule.
The default is `False`.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
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

### -DohTemplate
Specifies a valid URI template used to connect to the DoH server.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServerAddress
Specifies the IP address of the DoH server.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
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
Aliases: cf

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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.Boolean

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Add-DnsClientNrptRule](Add-DnsClientNrptRule.md)

[Get-DnsClientDohServerAddress](Get-DnsClientDohServerAddress.md)

[Remove-DnsClientDohServerAddress](Remove-DnsClientDohServerAddress.md)

[Set-DnsClientDohServerAddress](Set-DnsClientDohServerAddress.md)
