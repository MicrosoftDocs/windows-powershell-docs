---
description: The Set-DnsClientDohServerAddress cmdlet modifies an existing DNS-over-HTTPS (DoH) server configuration.
external help file: MSFT_DnsClientDohServerAddress.cdxml-help.xml
Module Name: DnsClient
ms.date: 08/31/2021
online version: https://learn.microsoft.com/powershell/module/dnsclient/set-dnsclientdohserveraddress?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-DnsClientDohServerAddress
---

# Set-DnsClientDohServerAddress

## SYNOPSIS
Modifies an existing DoH server configuration.

## SYNTAX

### Query (cdxml) (Default)
```
Set-DnsClientDohServerAddress [-ServerAddress] <String[]> [[-DohTemplate] <String>]
 [[-AllowFallbackToUdp] <Boolean>] [[-AutoUpgrade] <Boolean>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject (cdxml)
```
Set-DnsClientDohServerAddress -InputObject <CimInstance[]> [[-DohTemplate] <String>]
 [[-AllowFallbackToUdp] <Boolean>] [[-AutoUpgrade] <Boolean>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-DnsClientDohServerAddress** cmdlet modifies an existing DNS-over-HTTPS (DoH) server configuration.

## EXAMPLES

### Example 1: Change the URI template for a DoH server
```powershell
Set-DnsClientDohServerAddress -ServerAddress 10.23.1.1 -DohTemplate https://adatum.com/dns-query
```

This example changes the URI template for 10.23.1.1.
The command sets the **AutoUpgrade** and **AllowFallbackToUdp** values to the default value `False`.

### Example 2: Change the URI template for a DoH server with automatic upgrade
```powershell
Set-DnsClientDohServerAddress -ServerAddress 10.23.1.1 -DohTemplate https://adatum.com/dns-query -AutoUpgrade $True
```

This example changes the URI template for 10.23.1.1.
The command also upgrades any resolutions to 10.23.1.1.
The **AllowFallbackToUdp** parameter value defaults to `False`.
If the encrypted name resolution fails, it does not revert to unencrypted DNS.


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

### -InputObject
Specifies the input to this cmdlet.
You can use this parameter, or you can pipe the input to this cmdlet.

```yaml
Type: CimInstance[]
Parameter Sets: InputObject (cdxml)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### -ServerAddress
Specifies the IP address of the DoH server.

```yaml
Type: String[]
Parameter Sets: Query (cdxml)
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

### System.String[]

### Microsoft.Management.Infrastructure.CimInstance[]

### System.String

### System.Boolean

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_DNSClientDohServerAddress

## NOTES

## RELATED LINKS

[Add-DnsClientDohServerAddress](Add-DnsClientDohServerAddress.md)

[Add-DnsClientNrptRule](Add-DnsClientNrptRule.md)

[Get-DnsClientDohServerAddress](Get-DnsClientDohServerAddress.md)

[Remove-DnsClientDohServerAddress](Remove-DnsClientDohServerAddress.md)
