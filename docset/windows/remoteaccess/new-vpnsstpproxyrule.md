---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_VpnSstpProxyRule_v1.0.cdxml-help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: New-VpnSstpProxyRule
ms.reviewer:
ms.assetid: 2A16865C-54EC-45E0-A7F5-323758655FA4
---

# New-VpnSstpProxyRule

## SYNOPSIS
Creates a tenant ID to gateway mapping object.

## SYNTAX

```
New-VpnSstpProxyRule [-TenantID] <String> [-GatewayAddress] <String[]> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **New-VpnSstpProxyRule** cmdlet creates a tenant ID to gateway mapping object.

## EXAMPLES

### Example 1: Create a VPN SSTP Proxy rule
```
PS C:\>$Rule = New-VpnSstpProxyRule -TenantID "Contoso" -Gateway "100.10.10.10"
```

This command creates a VPN SSTP proxy rule with a tenant ID named Contoso.

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
Enter a computer name or a session object, such as the output of a [New-CimSession](http://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](http://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
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

### -GatewayAddress
Specifies the gateway IP address or the name for the tenant.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TenantID
Specifies the tenant ID or group ID to configure the SSTP proxy mapping.

```yaml
Type: String
Parameter Sets: (All)
Aliases: GroupID

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ThrottleLimit
Specifies the maximum number of concurrent connections that can be established to run this command.
If you omit this parameter or enter a value of 0, the default value, 32, is used.

The throttle limit applies only to the current command, not to the session or to the computer.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#VpnSstpProxyRule

## NOTES

## RELATED LINKS

[Add-VpnSstpProxyRule](./Add-VpnSstpProxyRule.md)

[Get-VpnSstpProxyRule](./Get-VpnSstpProxyRule.md)

[Remove-VpnSstpProxyRule](./Remove-VpnSstpProxyRule.md)

[Set-VpnSstpProxyRule](./Set-VpnSstpProxyRule.md)

[Remote Access Cmdlets](./remoteaccess.md)

