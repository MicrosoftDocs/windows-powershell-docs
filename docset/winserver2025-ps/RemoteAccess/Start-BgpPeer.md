---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_BgpPeer_v1.0.cdxml-help.xml
Module Name: RemoteAccess
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/remoteaccess/start-bgppeer?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Start-BgpPeer
---

# Start-BgpPeer

## SYNOPSIS
Starts routing sessions for BGP peers.

## SYNTAX

```
Start-BgpPeer [-RoutingDomain <String>] [-Name] <String[]> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Start-BgpPeer** cmdlet starts routing sessions for Border Gateway Protocol (BGP) peers.
Use the Stop-BgpPeer cmdlet to stop a routing session.
By default, when you add a peer by using the Add-BgpPeer cmdlet, exchange of route information begins immediately.
If you add a peer in manual peering mode, use this cmdlet to start the session.

## EXAMPLES

### Example 1: Start a routing session
```
PS C:\> Start-BgpPeer -Name "Site17"
```

This command starts a BGP routing session for the BGP router named Site17.

### Example 2: Start a routing session in a multitenant environment
```
PS C:\> Start-BgpPeer -Name "Tenant22" -RoutingDomain "Rd001"
```

This command starts a routing session for the peer named Tenant22 in the specified routing domain of a multitenant environment.

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

### -Name
Specifies an array of names.
The cmdlet starts routing sessions for the named peers.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.String[]

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Add-BgpPeer](./Add-BgpPeer.md)

[Get-BgpPeer](./Get-BgpPeer.md)

[Remove-BgpPeer](./Remove-BgpPeer.md)

[Set-BgpPeer](./Set-BgpPeer.md)

[Stop-BgpPeer](./Stop-BgpPeer.md)

