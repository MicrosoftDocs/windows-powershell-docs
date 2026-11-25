---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DAClientDNSConfiguration_v1.0.0.cdxml-help.xml
Module Name: RemoteAccess
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/remoteaccess/add-daclientdnsconfiguration?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-DAClientDnsConfiguration
---

# Add-DAClientDnsConfiguration

## SYNOPSIS
Adds the specified DNS suffix, DNS server addresses, or proxy server set to the Name Resolution Policy Table (NRPT).

## SYNTAX

```
Add-DAClientDnsConfiguration [[-DnsIPAddress] <String[]>] [-DnsSuffix] <String> [-ProxyServer <String>]
 [-ComputerName <String>] [-PassThru] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-DAClientDNSConfiguration** cmdlet adds the specified DNS suffix, DNS server addresses, or proxy server set to the Name Resolution Policy Table (NRPT).
When a DNS suffix is specified, but no servers are specified, it is treated as a NRPT exemption entry.

In a multi-domain deployment, when an NRPT entry that consists of DNS suffix, proxy server and DNS IP addresses is added to the NRPT table the settings are added to all the DirectAccess (DA) client Group Policy Objects (GPOs) in different domains.
In multi-site deployment with firstref_client_7 clients, the added entries are added to both the Windows® 8 client GPOs and Windows® 7 client GPOs.

The NRPT configuration is applicable globally, to the entire DA deployment and therefore is not impacted by multi-site deployment.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Add-DAClientDNSConfiguration -DnsSuffix contoso.com -DnsIPAddress 2006:2005:1::2 -PassThru
Comment                          :
DirectAccessDnsServers           : {2006:2005:1::2}
DirectAccessEnabled              : True
DirectAccessProxyName            :
DirectAccessProxyType            : Direct
DirectAccessQueryIPsecEncryption : None
DirectAccessQueryIPsecRequired   : False
DisplayName                      :
DnsSecEnabled                    :
DnsSecQueryIPsecEncryption       : None
DnsSecQueryIPsecRequired         : False
DnsSecValidationRequired         : False
IPsecCARestriction               :
Name                             : DA-{64329e4f-bd27-4d27-9553-6ed6880fa2a5}
NameEncoding                     :
NameServers                      :
Namespace                        : {contoso.com}
Version                          : 1
```

This example will add an entry for contoso.com into the NRPT which will result in all the DNS queries for the suffix contoso.com to be sent to 2006:2005:1::2 server.

### EXAMPLE 2
```
PS C:\>Add-DAClientDNSConfiguration -DnsSuffix corp.contoso.com -PassThru
Comment                          :
DirectAccessDnsServers           :
DirectAccessEnabled              : True
DirectAccessProxyName            :
DirectAccessProxyType            : Direct
DirectAccessQueryIPsecEncryption : None
DirectAccessQueryIPsecRequired   : False
DisplayName                      :
DnsSecEnabled                    :
DnsSecQueryIPsecEncryption       : None
DnsSecQueryIPsecRequired         : False
DnsSecValidationRequired         : False
IPsecCARestriction               :
Name                             : DA-{2cc7ec6f-9f80-4190-95cd-b9ee9cbd11a6}
NameEncoding                     :
NameServers                      :
Namespace                        : {corp.contoso.com}
Version                          : 1
```

This example will add an exempt entry for corp.contoso.com in the NRPT which will result in DNS queries for the suffix corp.contoso.com to not go to a DNS server in the corporate network for resolution.

There are some names that need to be treated differently from all others with regards to name resolution; these names must not be resolved using intranet DNS servers.
To ensure that these names are resolved with interface-configured DNS servers, these must added as NRPT exemptions.

There are several names that should be included on the exemption list - but the most important one is the name of the Network Location Server.
This prevents the DA client from being able to connect to the NLS server when the server is off network and therefore prevents it from mistakenly thinking that it is on the corporate network.

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
Specifies the IPv4 or IPv6 address of the corresponding DNS servers that should be used for the specified DNS suffix.
This parameter can be used with the **DnsSuffix** parameter.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: DirectAccessDnsServers

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DnsSuffix
Specifies a single DNS suffix.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Namespace

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

### -ProxyServer
Specifies the IPv4 or IPv6 address, or host name, of the proxy server configured for web traffic.
The proxy server is specified in either the `\<Proxy_Hostname\>:\<port\>` or the `\<Proxy_IPAddress\>:\<port\>` format.

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

### System.String[]

### System.String

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#DnsClientNRPTRule

The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

The DnsClientNRPTRule object consists of the following properties:

 -- The NRPT object for the NRPT entry that was added.

## NOTES

## RELATED LINKS

[Get-DAClientDnsConfiguration](./Get-DAClientDnsConfiguration.md)

[Remove-DAClientDnsConfiguration](./Remove-DAClientDnsConfiguration.md)

[Set-DAClientDnsConfiguration](./Set-DAClientDnsConfiguration.md)

