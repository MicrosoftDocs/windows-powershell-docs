---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_RemoteAccessLoadBalancerNode_v1.0.0.cdxml-help.xml
Module Name: RemoteAccess
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/remoteaccess/remove-remoteaccessloadbalancernode?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-RemoteAccessLoadBalancerNode
---

# Remove-RemoteAccessLoadBalancerNode

## SYNOPSIS
Removes a server from the network load balancing (NLB) cluster.

## SYNTAX

```
Remove-RemoteAccessLoadBalancerNode [-RemoteAccessServer] <String> [-ComputerName <String>] [-PassThru]
 [-Force] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-RemoteAccessLoadBalancerNode** cmdlet removes a server from the network load balancing (NLB) cluster.

When a server is removed, DirectAccess (DA) and VPN configuration settings on it are also removed.

When the last server from a cluster is removed, the DA and VPN configuration on it is not removed.

A server can be removed from the NLB cluster even if it is not reachable.

When VPN and DA configuration are cleared the Remote Access role is not uninstalled automatically.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Remove-RemoteAccessLoadBalancerNode -RemoteAccessServer edge3.corp.contoso.com -ComputerName edge2.corp.contoso.com
Confirm
Removing server edge3 from the load balanced cluster will reduce cluster capacity and availability. Do you want to remove the server?

[Y] Yes  [N] No  [S] Suspend  [?] Help (default is ꞌYꞌ): Y

In case edge3 is not a part of the NLB cluster that contains edge2, this cmdlet returns with the following message.
PS C:\>
Remove-RemoteAccessLoadBalancerNode: Server edge3 is not a part of a remote access server cluster
```

This example removes a server from an NLB Node.

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

### -ComputerName
Specifies the IPv4 orIPv6 address, or host name, of the server on which the cmdlet runs.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Cn

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

### -RemoteAccessServer
Specifies the IPv4 orIPv6 address, or host name, of the server that will be removed from the NLB cluster.

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

### System.String

## OUTPUTS

### System.String
The String consists of the following properties:

 -- The address (IPv4 or IPv6) or name of the server that was removed from the cluster.

## NOTES

## RELATED LINKS

[Add-RemoteAccessLoadBalancerNode](./Add-RemoteAccessLoadBalancerNode.md)

