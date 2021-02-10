---
external help file: VpnClient_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: 642D266F-03EC-4C92-AC30-DDA6B27EF2AA
manager: dansimp
---

# Set-VpnConnectionProxy

## SYNOPSIS
Configures web proxy information for the specified VPN connection.

## SYNTAX

```
Set-VpnConnectionProxy [-Name] <String> [-AutoConfigurationScript <String>] [-AutoDetect]
 [-BypassProxyForLocal] [-ExceptionPrefix <String[]>] [-ProxyServer <String>]
```

## DESCRIPTION
The **Set-VpnConnectionProxy** cmdlet configures web proxy information for the specified VPN connection.
If errors occur when you modify the web proxy information, the error information is returned.

## EXAMPLES

### Example 1: Configure the proxy settings for a VPN connection profile
```powershell
PS C:\>Set-VpnConnectionProxy -Name Contoso -ProxyServer 10.0.0.1:8080 -BypassProxyForLocal
```


This command sets the proxy configuration for the VPN connection named Contoso to use the proxy server with IP address 10.0.0.1 over port 8080, as specified by the _ProxyServer_ parameter.
The command also specifies that internal IP addresses are not routed to the proxy server, as specified by the _BypassProxyForLocal_ parameter.

### Example 2: Configure proxy and exclude based on domain and network
```powershell
PS C:\>Set-VpnConnectionProxy -Name "Contoso" -ProxyServer "10.0.0.1:8080" -ExcludePrefix '10.', '*.microsoft.com'
```

This command also sets the proxy for Contoso VPN and also specifies prefixes for addresses that will not use proxy via the _ExcludePrefix_ parameter. This exclude 10.0.0.0/8 and *.microsoft.com.

## PARAMETERS

### -AutoConfigurationScript
Specifies the name of the automatic WPAD configuration script that the specified connection uses.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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
Accept pipeline input: False
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
Accept pipeline input: False
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
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the VPN connection for which the proxy settings are configured.

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
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-VpnConnection](./Get-VpnConnection.md)

