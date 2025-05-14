---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_VpnSstpProxyRule_v1.0.cdxml-help.xml
Module Name: RemoteAccess
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/remoteaccess/get-vpnsstpproxyrule?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-VpnSstpProxyRule
---

# Get-VpnSstpProxyRule

## SYNOPSIS
Retrieves the Tenant ID to gateway mapping.

## SYNTAX

```
Get-VpnSstpProxyRule [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-VpnSstpProxyRule** cmdlet retrieves the Tenant ID to gateway mappings.

## EXAMPLES

### Example 1: Get all the VPN SSTP proxy rules configured on the server
```
PS C:\>Get-VpnSstpProxyRule
```

This command gets all the VPN SSTP proxy rules configured on the server.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

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

### -ThrottleLimit
Specifies the maximum number of concurrent connections that can be established to run this command.
If you omit this parameter or enter a value of 0, the default value, 32, is used.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance[]

### Microsoft.Management.Infrastructure.CimInstance#VpnSstpProxyRule

## NOTES

## RELATED LINKS

[Add-VpnSstpProxyRule](./Add-VpnSstpProxyRule.md)

[New-VpnSstpProxyRule](./New-VpnSstpProxyRule.md)

[Remove-VpnSstpProxyRule](./Remove-VpnSstpProxyRule.md)

[Set-VpnSstpProxyRule](./Set-VpnSstpProxyRule.md)

[Remote Access Cmdlets](./remoteaccess.md)

