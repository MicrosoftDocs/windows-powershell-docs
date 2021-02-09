---
external help file: WSS_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: 048C2958-E203-448F-ABB1-1D11FFBA4DA1
manager: dansimp
---

# Install-WssVpnServer

## SYNOPSIS
Installs a VPN server.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Install-WssVpnServer [-ApplyToExistingUsers] [-AutoDetect] [-DenyAccessByDefault] [-NoSkip] [-Confirm]
 [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Install-WssVpnServer [[-IPv4AddressRange] <IPAddress[]>] [[-IPv6AddressPrefix] <IPAddress>]
 [-ApplyToExistingUsers] [-DenyAccessByDefault] [-NoSkip] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Install-WssVpnServer [-ApplyToExistingUsers] [-DenyAccessByDefault] [-NoSkip] [-UseDhcp] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Install-WssVpnServer** cmdlet installs a VPN server on sbs_sbs8_2.

## EXAMPLES

### Example 1: Install a VPN server
```
PS C:\> Install-WssVpnServer -AutoDetect
```

This command installs a VPN server.

## PARAMETERS

### -ApplyToExistingUsers
Indicates that access is granted to existing users.

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

### -AutoDetect
Indicates that the VPN server automatically detect best-fit settings, regardless of previous settings.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DenyAccessByDefault
Indicates that the VPN server deny access by default.

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

### -IPv4AddressRange
Specifies an array of IPv4 addresses for the static IP address pool.

```yaml
Type: IPAddress[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPv6AddressPrefix
Specifies the prefix of IPv6 addresses for the static IP address pool.

```yaml
Type: IPAddress
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoSkip
Indicates that the VPN server installation runs, even if there are no changes to the previous installation.

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

### -UseDhcp
Indicates that DHCP assigns IP addresses to VPN clients.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_3
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
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Test-WssVpnServerInstallation](./Test-WssVpnServerInstallation.md)

[Uninstall-WssVpnServer](./Uninstall-WssVpnServer.md)

