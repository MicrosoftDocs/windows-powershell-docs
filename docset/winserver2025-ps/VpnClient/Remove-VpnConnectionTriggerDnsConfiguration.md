---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_VpnConnectionTriggerDnsConfiguration_v1.0.cdxml-help.xml
Module Name: VpnClient
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/vpnclient/remove-vpnconnectiontriggerdnsconfiguration?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-VpnConnectionTriggerDnsConfiguration
---

# Remove-VpnConnectionTriggerDnsConfiguration

## SYNOPSIS
Removes DNS suffixes from VPN connection DNS trigger properties.

## SYNTAX

```
Remove-VpnConnectionTriggerDnsConfiguration [-ConnectionName] <String> [-DnsSuffix] <String[]> [-PassThru]
 [-Force] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-VpnConnectionTriggerDnsConfiguration** cmdlet removes Domain Name System (DNS) suffixes from the DNS trigger properties for a virtual private network (VPN) connection.
After you remove a DNS suffix, if the client accesses any resource that is part of the DNS suffix, accessing that resource does not trigger a VPN connection.
VPN connection DNS trigger properties determine whether a client automatically starts an existing VPN connection.

If you previously ran the Set-VpnConnectionTriggerTrustedNetwork cmdlet with the *DefaultDnsSuffixes* parameter specified, the current cmdlet also removes the DNS suffixes from the trusted network list.

## EXAMPLES

### Example 1: Remove DNS suffixes for a connection
```
PS C:\>Remove-VpnConnectionTriggerDnsConfiguration -ConnectionName "Contoso" -DnsSuffix "washington.contoso.com", "newyork.contoso.com" -Force
```

This command removes the DNS suffixes washington.contoso.com and newyork.contoso.com for the VPN connection profile named Contoso.
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

### -DnsSuffix
Specifies an array of DNS suffixes.

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

### -Force
Indicates that the cmdlet removes DNS suffixes from the VPN connection trigger DNS configuration without a confirmation message.

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

[Set-VpnConnectionTriggerDnsConfiguration](./Set-VpnConnectionTriggerDnsConfiguration.md)

[Set-VpnConnectionTriggerTrustedNetwork](./Set-VpnConnectionTriggerTrustedNetwork.md)

