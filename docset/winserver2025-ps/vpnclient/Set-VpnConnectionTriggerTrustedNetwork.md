---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_VpnConnectionTriggerTrustedNetwork_v1.0.cdxml-help.xml
Module Name: VpnClient
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/vpnclient/set-vpnconnectiontriggertrustednetwork?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-VpnConnectionTriggerTrustedNetwork
---

# Set-VpnConnectionTriggerTrustedNetwork

## SYNOPSIS
Sets the trusted network list.

## SYNTAX

```
Set-VpnConnectionTriggerTrustedNetwork [-ConnectionName] <String> [-DefaultDnsSuffixes] [-PassThru] [-Force]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-VpnConnectionTriggerTrustedNetwork** cmdlet sets the trusted network list.
The cmdlet sets the trusted network list with the Domain Name System (DNS) suffixes in the name resolution policy table (NRPT) that are configured as part of triggering properties.
The cmdlet ignores NRPT exemption entries.

## EXAMPLES

### Example 1: Set the trusted network list
```
PS C:\>Get-VpnConnectionTrigger -ConnectionName "ContosoVPN"
PS C:\> Set-VpnConnectionTriggerTrustedNetwork -ConnectionName "ContosoVPN" -DefaultDnsSuffixes -PassThru -Force
ConnectionName : Contoso
DnsSuffix      : {newyork.contoso.com, washington.contoso.com}
```

This example sets the trusted network list for a VPN connection profile.

The first command uses the Get-VpnConnectionTrigger cmdlet to get the trigger properties of a VPN connection named ContosoVPN.

The second command sets the trusted network list for the VPN connection named ContosoVPN with the DNS suffixes in the NRPT that are configured as part of triggering properties.
The *DefaultDnsSuffixes* parameter specifies that the server copies all DNS suffixes in the **VpnConnectionTriggerDnsConfiguration** object that have corresponding server addresses into the DNS suffixes for **VpnConnectionTriggerTrustedNetwork**.

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

### -DefaultDnsSuffixes
Indicates that this cmdlet copies all DNS suffixes in the **VpnConnectionTriggerDnsConfiguration** object into the DNS suffixes for **VpnConnectionTriggerTrustedNetwork**.
This cmdlet does not copy DNS suffixes without corresponding DNS servers.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Force
Indicates that the cmdlet replaces the current trusted network list of with the DNS suffixes in **VpnConnectionTriggerDnsConfiguration** without a confirmation message.

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
If you specify this parameter, the cmdlet returns the **VpnConnectionTriggerTrustedNetwork** object that contains the list of trusted networks for triggering.

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

### Microsoft.Management.Infrastructure.CimInstance#VpnConnectionTriggerTrustedNetwork

## NOTES

## RELATED LINKS

[Add-VpnConnectionTriggerTrustedNetwork](./Add-VpnConnectionTriggerTrustedNetwork.md)

[Get-VpnConnection](./Get-VpnConnection.md)

[Get-VpnConnectionTrigger](./Get-VpnConnectionTrigger.md)

[Remove-VpnConnectionTriggerTrustedNetwork](./Remove-VpnConnectionTriggerTrustedNetwork.md)

