---
external help file: WssCmdlets.dll-Help.xml
Module Name: WSSCmdlets
ms.date: 12/05/2017
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/install-wssvpnserver?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Install-WssVpnServer
---

# Install-WssVpnServer

## SYNOPSIS
Installs a VPN server.

## SYNTAX

### auto (Default)
```
Install-WssVpnServer [-AutoDetect] [-NoSkip] [-DenyAccessByDefault] [-ApplyToExistingUsers] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### dhcp
```
Install-WssVpnServer [-UseDhcp] [-NoSkip] [-DenyAccessByDefault] [-ApplyToExistingUsers] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### pool
```
Install-WssVpnServer [-NoSkip] [[-IPv4AddressRange] <IPAddress[]>] [[-IPv6AddressPrefix] <IPAddress>]
 [-DenyAccessByDefault] [-ApplyToExistingUsers] [-WhatIf] [-Confirm] [<CommonParameters>]
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
Parameter Sets: auto
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
Default value: False
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
Parameter Sets: pool
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPv6AddressPrefix
Specifies the prefix of IPv6 addresses for the static IP address pool.

```yaml
Type: IPAddress
Parameter Sets: pool
Aliases: 

Required: False
Position: 1
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
Parameter Sets: dhcp
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Test-WssVpnServerInstallation](./Test-WssVpnServerInstallation.md)

[Uninstall-WssVpnServer](./Uninstall-WssVpnServer.md)

