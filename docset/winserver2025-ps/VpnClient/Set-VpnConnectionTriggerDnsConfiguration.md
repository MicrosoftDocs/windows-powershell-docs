---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_VpnConnectionTriggerDnsConfiguration_v1.0.cdxml-help.xml
Module Name: VpnClient
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/vpnclient/set-vpnconnectiontriggerdnsconfiguration?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-VpnConnectionTriggerDnsConfiguration
---

# Set-VpnConnectionTriggerDnsConfiguration

## SYNOPSIS
Changes DNS servers for an existing DNS suffix.

## SYNTAX

```
Set-VpnConnectionTriggerDnsConfiguration [-ConnectionName] <String> [[-DnsSuffix] <String>]
 [[-DnsIPAddress] <String[]>] [[-DnsSuffixSearchList] <String[]>] [-PassThru] [-Force]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-VpnConnectionTriggerDnsConfiguration** cmdlet changes Domain Name System (DNS) servers for a DNS suffix that is associated with a virtual private network (VPN) connection.
This cmdlet also configures the DNS suffix search list for a VPN connection.

If you specify a DNS IP address for a suffix, when a client accesses a resource within that suffix, the client starts a VPN connection.
You can specify a list of DNS suffixes for a client to append to short names to try connections by using a specified VPN connection.

## EXAMPLES

### Example 1: Change the DNS server for a DNS suffix
```
PS C:\>Set-VpnConnectionTriggerDnsConfiguration -ConnectionName "Contoso" -DnsSuffix "washington.contoso.com" -DnsIPAddress "172.16.12.3" -PassThru -Force
ConnectionName       DnsSuffix            DnsIPAddress                             DnsSuffixSearchList

--------------       ---------            ------------                             -------------------

Contoso              washington.contos... {207.64.32.54}
```

This command changes the IP address for the DNS server for a DNS suffix to a value of 172.16.12.3.
Use the *DnsIPAddress* parameter to specify the new value.
The command specifies the VPN connection profile named Contoso and the DNS suffix washington.contoso.com.
The command includes the *PassThru* parameter.
Therefore, it returns the VPN connection DNS trigger properties for the client.
Because the command includes the *Force* parameter, it does not prompt you for confirmation.

### Example 2: Change the DNS suffix search list for a VPN connection
```
PS C:\>Set-VpnConnectionTriggerDnsConfiguration -ConnectionName "Contoso" -DnsSuffixSearchList "corp.contoso.com", "sales.Contoso.com" -PassThru -Force
ConnectionName       DnsSuffix            DnsIPAddress                             DnsSuffixSearchList

--------------       ---------            ------------                             -------------------

Contoso                                                                            {corp.contoso.com, sales.contoso....
```

This command changes the DNS suffix search list for the VPN connection profile named Contoso to be the two specified DNS suffixes.
The command includes the *PassThru* parameter.
Therefore, it returns the VPN connection DNS trigger properties for the client.
Because the command includes the *Force* parameter, it does not prompt you for confirmation.

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
If you specify an empty string, when the client accesses a resource in the DNS suffix, it does not trigger a VPN connection.

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

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DnsSuffixSearchList
Specifies an array of DNS suffixes.
The client appends a suffix to a short name to create a fully qualified domain name (FQDN).
The client tries the suffixes on this list to see if any of them, appended to a short name, identify a resource.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Force
Indicates that the cmdlet makes changes to the VPN connection trigger DNS configuration without a confirmation message.

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
If you specify this parameter, the cmdlet returns the **VpnConnectionTriggerDnsConfiguration** object that contains DNS suffixes and corresponding DNS servers, and the DNS suffix search list.

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

[Add-VpnConnectionTriggerDnsConfiguration](./Add-VpnConnectionTriggerDnsConfiguration.md)

[Get-VpnConnection](./Get-VpnConnection.md)

[Remove-VpnConnectionTriggerDnsConfiguration](./Remove-VpnConnectionTriggerDnsConfiguration.md)

