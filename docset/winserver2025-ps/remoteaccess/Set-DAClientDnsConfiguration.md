---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DAClientDNSConfiguration_v1.0.0.cdxml-help.xml
Module Name: RemoteAccess
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/remoteaccess/set-daclientdnsconfiguration?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-DAClientDnsConfiguration
---

# Set-DAClientDnsConfiguration

## SYNOPSIS
Configures the DNS server and proxy server addresses of a Name Resolution Policy Table (NRPT) entry and configures the local name resolution property.

## SYNTAX

```
Set-DAClientDnsConfiguration [-DnsSuffix <String>] [-DnsIPAddress <String[]>] [-ProxyServer <String>]
 [-Local <String>] [-ComputerName <String>] [-PassThru] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-DAClientDnsConfiguration** cmdlet configures the DNS server and proxy server addresses of a Name Resolution Policy Table (NRPT) entry and configures the local name resolution property.

To modify an NRPT entry the user needs to specify the DNS suffix, the new DNS IP address or the proxy server, or the new DNS IP address and the proxy server for this suffix.
To modify the local name resolution setting the **Local** parameter is used.

When an NRPT entry or local name resolution property is modified in a multi-domain scenario, it is correspondingly updated in all of the client Group Policy Objects (GPOs) in various domains.
This is true for multi-site and firstref_server_7 GPOs as well.

The NRPT configuration is applicable globally to the entire DirectAccess (DA) deployment and therefore is not impacted by multi-site deployment.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Set-DAClientDNSConfiguration -DNSSuffix 'contoso.com' -DnsIPAddress 2006:2005:1::3
```

This example will change the list of configured DNS Servers for contoso.com to 2006:2005:1::3.
These changes will be made in all of the DA client GPOs.

### EXAMPLE 2
```
PS C:\>Set-DAClientDNSConfiguration -DNSSuffix 'contoso.com' -ProxyServer 'webproxy.contoso.com:400'
```

This example configures a proxy server for suffix contoso.com.
Since NRPT entry settings in DA are global, this change will apply to all of the DA clients.

### EXAMPLE 3
```
PS C:\>Set-DAClientDnsConfiguration -Local 'FallbackSecure'
```

This example configures local name resolution to FallbackSecure, therefore ensuring that local name resolution is used only if the resource name does not exist in DNS.

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

### -ComputerName
Specifies the IPv4 or IPv6 address, or host name, of the computer on which the Remote Access server computer specific tasks should be run.

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

### -DnsIPAddress
Specifies the new list of DNS server IPv4 or IPv6 addresses for the specified DNS suffix in the NRPT.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: DirectAccessDnsServers

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DnsSuffix
Specifies the DNS suffix entry in the NRPT that needs to be modified.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Namespace

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Local
Specifies the property of the local name resolution.
The acceptable values for this parameter are:

 -- FallbackSecure: Only use local name resolution if the name does not exist in DNS, which is most restrictive.

 -- FallbackPrivate: Fall back to local name resolution if the name does not exist in the DNS or the DNS servers are unreachable when the client computer is on a private network, which is recommended.

 -- FallbackUnsecure: Fall back to local name resolution for any kind of DNS resolution error, which is least secure.

```yaml
Type: String
Parameter Sets: (All)
Aliases: SecureNameQueryFallback
Accepted values: FallbackSecure, FallbackPrivate, FallbackUnsecure

Required: False
Position: Named
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

### -ProxyServer
Specifies the new proxy server for the specified DNS suffix in the NRPT.

```yaml
Type: String
Parameter Sets: (All)
Aliases: DirectAccessProxyName

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

### System.String

### System.String[]

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#DAClientDnsConfiguration

The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

The DAClientDnsConfiguration object contains the following properties:

 -- The NRPT entries in the NRPT table: each entry is an instance of the DnsClientNrptRule object.

 -- The DnsClientNrptGlobal object which contains the local name resolution settings.

## NOTES

## RELATED LINKS

[Add-DAClientDnsConfiguration](./Add-DAClientDnsConfiguration.md)

[Get-DAClientDnsConfiguration](./Get-DAClientDnsConfiguration.md)

[Remove-DAClientDnsConfiguration](./Remove-DAClientDnsConfiguration.md)

