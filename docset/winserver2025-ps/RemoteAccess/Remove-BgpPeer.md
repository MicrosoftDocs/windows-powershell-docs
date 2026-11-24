---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_BgpPeer_v1.0.cdxml-help.xml
Module Name: RemoteAccess
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/remoteaccess/remove-bgppeer?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-BgpPeer
---

# Remove-BgpPeer

## SYNOPSIS
Removes BGP peers from a router.

## SYNTAX

```
Remove-BgpPeer [-Name] <String[]> [-RoutingDomain <String>] [-Force] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-BgpPeer** cmdlet removes Border Gateway Protocol (BGP) peers from a BGP router.
Specify a peer to remove by using its name.
This cmdlet does not uninstall the peer router software.
When you remove a peer, the router removes all information collected from the peer.

## EXAMPLES

### Example 1: Remove specified peers
```
PS C:\> Remove-BgpPeer -Name TenantSite22,TenantSite23
Confirm
BGP peering session is active with peer TenantSite22. Do you want to stop peering and remove this peer?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): y

Confirm
BGP peering session is active with peer TenantSite23. Do you want to stop peering and remove this peer?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): y
```

This command removes the peers named TenantSite22 and TenantSite23.
This command does not specify the **Force** parameter, so it prompts you before it removes the peers.

### Example 2: Remove all peers
```
PS C:\> Get-BgpPeer | Remove-BgpPeer -Force
```

This command gets all the peers by using the Get-BgpPeer cmdlet, and passes them to the current cmdlet by using the pipeline operator.
The command removes all the peers.
Because the command specifies the Force parameter, it does not prompt you for confirmation before it removes the peers.

### Example 3: Remove all peers in a routing domain
```
PS C:\> Remove-BgpPeer -Name "Tenant16" -Force -RoutingDomain "Rd001"
```

This command removes the peer named Tenant16 in the routing domain Rd001 without prompting you for confirmation.

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

### -Name
Specifies an array of names.
The cmdlet removes the named peers.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: PeerList, PeerId, PeerName

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RoutingDomain
Specifies the name of the routing domain as a string.
The name is a unique, for the multitenant gateway, user-defined alphanumeric string.

```yaml
Type: String
Parameter Sets: (All)
Aliases: RoutingDomainName

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

### System.Object

## NOTES

## RELATED LINKS

[Add-BgpPeer](./Add-BgpPeer.md)

[Get-BgpPeer](./Get-BgpPeer.md)

[Set-BgpPeer](./Set-BgpPeer.md)

[Start-BgpPeer](./Start-BgpPeer.md)

[Stop-BgpPeer](./Stop-BgpPeer.md)

