---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_VpnConnectionProxy_v1.0.cdxml-help.xml
Module Name: VpnClient
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/vpnclient/set-vpnconnectionproxy?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-VpnConnectionProxy
---

# Set-VpnConnectionProxy

## SYNOPSIS
Configures web proxy information for the specified VPN connection.

## SYNTAX

```
Set-VpnConnectionProxy [-AutoDetect] [-AutoConfigurationScript <String>] [-ProxyServer <String>]
 [-BypassProxyForLocal] [-ExceptionPrefix <String[]>] [-ConnectionName] <String> [-PassThru]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-VpnConnectionProxy** cmdlet configures web proxy information for the specified VPN connection.
If errors occur when you modify the web proxy information, the error information is returned.

Note that VPN proxy settings are only used on forced tunnel connections. On split tunnel connections, the general proxy settings are used.

## EXAMPLES

### Example 1: Configure the proxy settings for a VPN connection profile
```powershell
PS C:\>Set-VpnConnectionProxy -ConnectionName "Contoso" -ProxyServer "10.0.0.1:8080" -BypassProxyForLocal -PassThru
```

This command sets the proxy configuration for the VPN connection named Contoso to use the proxy server with IP address 10.0.0.1 over port 8080, as specified by the *ProxyServer* parameter.
The command also specifies that internal IP addresses are not routed to the proxy server, as specified by the *BypassProxyForLocal* parameter.

### Example 2: Configure proxy and exclude based on domain and network
```powershell
PS C:\>Set-VpnConnectionProxy -ConnectionName "Contoso" -ProxyServer "10.0.0.1:8080" -ExcludePrefix '10.', '*.microsoft.com'
```

This command also sets the proxy for Contoso VPN and also specifies prefixes for addresses that will not use proxy via the _ExcludePrefix_ parameter. This exclude 10.0.0.0/8 and *.microsoft.com.

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

### -AutoConfigurationScript
Specifies the name of the automatic WPAD configuration script that the specified connection uses.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AutoDetect
Indicates that proxy settings are automatically detected.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -BypassProxyForLocal
Indicates that the proxy configuration is bypassed for local addresses.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](/powershell/module/cimcmdlets/new-cimsession) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
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

### -ExceptionPrefix
Specifies the prefixes for internet addresses for which the proxy is not to be used.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

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
Specifies the web proxy server IP address and port number.
Specify the address and port separated by a colon.
For example, 10.0.0.1:8080.
If you do not specify the port number, port 80 is used.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

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

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-VpnConnection](./Get-VpnConnection.md)
