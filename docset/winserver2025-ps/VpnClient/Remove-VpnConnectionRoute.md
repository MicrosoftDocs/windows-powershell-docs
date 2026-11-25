---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_VpnConnectionRoute_v1.0.cdxml-help.xml
Module Name: VpnClient
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/vpnclient/remove-vpnconnectionroute?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-VpnConnectionRoute
---

# Remove-VpnConnectionRoute

## SYNOPSIS
Removes a route from a VPN connection.

## SYNTAX

```
Remove-VpnConnectionRoute [-ConnectionName] <String> [-DestinationPrefix] <String> [-AllUserConnection]
 [-PassThru] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-VpnConnectionRoute** cmdlet removes an IPv4 or IPv6 route from a VPN connection.

## EXAMPLES

### Example 1: Remove a VPN connection route for an IPv4 address
```
PS C:\> Remove-VpnConnectionRoute -ConnectionName "Contoso" -DestinationPrefix "176.16.0.0/16" -PassThru
DestinationPrefix : 176.16.0.0/16

InterfaceIndex    :
InterfaceAlias    : Contoso

AddressFamily     : IPv4

NextHop           : 0.0.0.0

Publish           : 0

RouteMetric       : 1

PolicyStore       :
```

This command uses the Remove-VpnConnectionRoute cmdlet to remove a route associated with an IPv4 address prefix.
The command specifies the *PassThru* parameter to return an object.

### Example 2: Remove a VPN connection route for an IPv6 address
```
PS C:\>Remove-VpnConnectionRoute -ConnectionName "Contoso" -DestinationPrefix "2001:4898:7020:3020::/64" -PassThru
DestinationPrefix : 2001:4898:7020:3020::/64

InterfaceIndex    :

InterfaceAlias    : Contoso

AddressFamily     : IPv6

NextHop           : ::

Publish           : 0

RouteMetric       : 23

PolicyStore       :
```

This command uses the **Remove-VpnConnectionRoute** cmdlet to remove a route associated with an IPv6 address prefix.
The command also specifies the *PassThru* parameter to return an object.

## PARAMETERS

### -AllUserConnection
Indicates that the VPN connection being modified is in the global phone book.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

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
Specifies the name of a VPN connection profile to modify.
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

### -DestinationPrefix
Specifies the destination prefix of the route to remove.

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

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.
If you specify this parameter, the cmdlet returns the **MSFT_NetRoute** object.

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

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_NetRoute

## NOTES

## RELATED LINKS

[Add-VpnConnectionRoute](./Add-VpnConnectionRoute.md)

