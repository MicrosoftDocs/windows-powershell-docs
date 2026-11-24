---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_VpnConnectionTriggerDnsConfiguration_v1.0.cdxml-help.xml
Module Name: VpnClient
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/vpnclient/add-vpnconnectiontriggerdnsconfiguration?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-VpnConnectionTriggerDnsConfiguration
---

# Add-VpnConnectionTriggerDnsConfiguration

## SYNOPSIS
Adds a DNS suffix or name to VPN connection trigger properties.

## SYNTAX

```
Add-VpnConnectionTriggerDnsConfiguration [-ConnectionName] <String> [-DnsSuffix] <String>
 [[-DnsIPAddress] <String[]>] [-PassThru] [-Force] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-VpnConnectionTriggerDnsConfiguration** cmdlet adds a Domain Name System (DNS) suffix or name to the DNS trigger properties for a client.
If you specify a DNS IP address for the suffix or name, when the client accesses a resource in the suffix, the client starts a virtual private network (VPN) connection.
If you do not specify a DNS IP address for a DNS suffix or name, accessing the suffix or name does not trigger the VPN connection.

If you previously ran the Set-VpnConnectionTriggerTrustedNetwork cmdlet with the *DefaultDnsSuffixes* parameter specified, the current cmdlet adds the DNS suffix to the trusted Network list.
This cmdlet does not add DNS suffixes that do not have DNS server addresses.

## EXAMPLES

### Example 1: Add a DNS suffix
```
PS C:\>Add-VpnConnectionTriggerDnsConfiguration -ConnectionName "Contoso" -DnsSuffix "washington.contoso.com" -DnsIPAddress "172.16.12.23" -PassThru
WARNING: The suffix washington.contoso.com will be automatically added to

the trusted network detection list. Any subsequent addition/removal of

suffixes from this cmdlet will be reflected in the trusted network

detection list. If you do not want this auto-population, remove the

suffixes from the trusted network detection list by using the

cmdlet Remove-VpnConnectionTriggerTrustedNetwork

ConnectionName       DnsSuffix            DnsIPAddress                             DnsSuffixSearchList

--------------       ---------            ------------                             -------------------

Contoso              washington.contos... {172.16.12.23}
```

This command adds the DNS suffix washington.contoso.com to the trigger properties for the current client.
The command specifies the VPN connection profile named Contoso and an address for a DNS server for this suffix.
The command includes the *PassThru* parameter.
Therefore, it returns the VPN connection DNS trigger properties for the client.

In this example, Trigger Trusted Network has the default value.
Therefore the command adds the suffix to the trusted network detection list.

### Example 2: Add a DNS suffix that has multiple DNS servers
```
PS C:\>Add-VpnConnectionTriggerDnsConfiguration -ConnectionName "Contoso" -DnsSuffix "newyork.contoso.com" -DnsIPAddress "172.16.12.3", "172.16.12.22" -PassThru
ConnectionName       DnsSuffix            DnsIPAddress                             DnsSuffixSearchList

--------------       ---------            ------------                             -------------------

Contoso              newyork.contoso.com  {172.16.12.3, 172.16.12.22}
```

This command adds the DNS suffix newyork.contoso.com to the trigger properties for the current client.
The command specifies the VPN connection profile named Contoso and multiple addresses for DNS servers.
The command includes the *PassThru* parameter.
Therefore, it returns the VPN connection DNS trigger properties for the client.

### Example 3: Add a DNS suffix that does not trigger a VPN connection
```
PS C:\>Add-VpnConnectionTriggerDnsConfiguration -ConnectionName "Contoso" -DnsSuffix "ras.washington.contoso.com" -PassThru
ConnectionName       DnsSuffix            DnsIPAddress                             DnsSuffixSearchList

--------------       ---------            ------------                             -------------------

Contoso              ras.washington.co...
```

This command adds the DNS suffix ras.washington.contoso.com to the trigger properties for the current client.
The command specifies the VPN connection profile named Contoso.
Unlike the previous examples, this command does not specify an address for a DNS server.
When this client accesses resources from ras.washington.contoso.com, it does not trigger a VPN connection.
The command includes the *PassThru* parameter.
Therefore, it returns the VPN connection DNS trigger properties for the client.

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

### -ConnectionName
Specifies the name of a VPN connection profile.
To view existing VPN connection profiles, use the Get-VpnConnection cmdlet.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Name

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DnsIPAddress
Specifies an array IP addresses of DNS servers for the DNS suffix.
You can use both IPv4 and IPv6 addresses.

If you do not specify a DNS server, the client does not start a VPN connection when the client accesses a resource with the DNS suffix or name.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DnsSuffix
Specifies a DNS suffix.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Force
Forces the command to run without asking for user confirmation.

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

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.
If you specify this parameter, the cmdlet returns the **VpnConnectionTriggerDnsConfiguration** object that contains DNS suffixes and corresponding DNS servers.

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

### Microsoft.Management.Infrastructure.CimInstance#VpnConnectionTriggerDnsConfiguration

## NOTES

## RELATED LINKS

[Get-VpnConnection](./Get-VpnConnection.md)

[Remove-VpnConnectionTriggerDnsConfiguration](./Remove-VpnConnectionTriggerDnsConfiguration.md)

[Set-VpnConnectionTriggerDnsConfiguration](./Set-VpnConnectionTriggerDnsConfiguration.md)

