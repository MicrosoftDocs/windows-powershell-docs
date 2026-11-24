---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_RemoteAccess_v1.0.0.cdxml-help.xml
Module Name: RemoteAccess
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/remoteaccess/uninstall-remoteaccess?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Uninstall-RemoteAccess
---

# Uninstall-RemoteAccess

## SYNOPSIS
Uninstalls DirectAccess (DA) and VPN, both Remote Access (RA) VPN and site-to-site VPN.

## SYNTAX

```
Uninstall-RemoteAccess [-VpnType <String>] [-ComputerName <String>] [-EntrypointName <String>] [-Force]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Unistall-RemoteAccess** cmdlet uninstalls DirectAccess (DA) and VPN, both Remote Access (RA) VPN and site-to-site VPN.

Users should indicate which RA technology to uninstall using the appropriate parameter.
If none of the technologies are specified, then everything gets uninstalled.

This cmdlet will not handle removal of RA role and other dependent roles.

Following is the list of scenarios supported or not supported by this cmdlet.

Single Site.

 -- If only VPN or S2S VPN has been configured, then it can be un-configured.

 -- If both DA and VPN have been configured, then VPN can be un-configured but DA alone cannot be un-configured.

 -- If both DA and S2S VPN have been configured, then S2S VPN can be un-configured but DA alone cannot be un-configured.

 -- If only DA is configured, then it can be un-configured.

Load balanced cluster.

 -- If both DA and VPN have been configured.

 ---- VPN can be un-configured.
Since VPN is configured for the cluster, removing it will remove VPN from the entire cluster.

 ---- Both DA and VPN can be un-configured.
This will remove the cluster settings as well as the RA settings from the deployment.

 -- If both DA and S2S VPN have been configured.

 ---- DA and S2S VPN can be un-configured.
Note: The S2S VPN can only be removed from the Computer mentioned in the cmdlet.
If it is present on other nodes in the deployment, it will not be removed from there.

 -- If only DA has been configured, then it can be un-configured as well.
This will remove the cluster settings as well as the DA settings from the deployment and bring it to un-configured state.
To uninstall DA on one of the nodes in a load balancing cluster, remove the node from the cluster using the Remove-RemoteAccessLoadBalancerNode cmdlet.

Multi-site deployment.

 -- If both DA and VPN have been configured.

 ---- VPN can be un-configured.
Since VPN is configured for a particular entry point, removing it will remove VPN from the entry point.
If there are multiple entrypoints in a deployment and VPN needs to be uninstalled completely, then it has to be uninstalled from each entry point separately.

 ---- Both DA and VPN can be un-configured.
This will remove the cluster settings as well as the RA settings from the deployment.

 -- If both DA and S2S VPN have been configured.

 ---- DA and S2S VPN can be un-configured.
Note: The S2S VPN can only be removed from the computer mentioned in the cmdlet.
If it is present on other nodes in the deployment, it will not be removed from there.

 -- If only DA has been configured, it can be un-configured as well.
This will remove DA settings from all the entry points in the deployment and bring it to un-configured state.
To uninstall DA from an entry point, use the Remove-DAEntryPoint cmdlet.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Uninstall-RemoteAccess
Confirm
If Remote Access is uninstalled, remote clients will not be able to connect to the corporate network via DirectAccess. The network location server running on the Remote Access server will be disabled, and DirectAccess clients will not be able to use it to detect their location. This will cause loss of connectivity to internal resources for clients located in the corporate network. Do you want to continue?

[Y] Yes  [N] No  [S] Suspend  [?] Help  (default is ꞌYꞌ): Y
```

This example uninstalls DA from all sites.
Before uninstalling it warns the users of the after effects.
Since the NLS is running on the DA server in this case the warning also describes the impact of uninstallation on the connectivity of clients when inside corporate network.

### EXAMPLE 2
```
PS C:\>Uninstall-RemoteAccess -VPNType VPN
Confirm
If RemoteAccess is uninstalled, remote clients will not be able to connect to corporate network via VPN. Do you want to continue?

[Y] Yes  [N] No  [S] Suspend  [?] Help  (default is ꞌYꞌ): Y
```

This example removes a VPN.
This cmdlet will first prompt to confirm before uninstalling a VPN.

### EXAMPLE 3
```
PS C:\>Uninstall-RemoteAccess
Confirm
If Remote Access is uninstalled, remote clients will not be able to connect to the corporate network via
DirectAccess + Vpn. Do you want to continue?

[Y] Yes  [N] No  [S] Suspend  [?] Help  (default is ꞌYꞌ): Y
```

This example uninstalls DA and VPN in a single site installation.
When run the cmdlets uninstalls both DA and VPN.
Care should be taken not to run this cmdlet flavor in a multisite environment with S2S VPN, since it would lead to a rather unexpected behavior where DA is un-installed and S2S VPN is uninstalled from the current computer, but the other end-point of the S2S VPN on a different computer or server will not be uninstalled.

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
Specifies the IPv4 orIPv6 address, or host name, of the computer on which the RA server computer specific tasks should be run.
If this parameter is specified and a user is trying to uninstall VPN then VPN on this RA server is uninstalled.

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

### -EntrypointName
Specifies the name of a site in a multisite deployment.
The cmdlet uninstalls VPN on this site.
In a multisite deployment, you must uninstall VPN on one site at a time.
This parameter does not apply to DA.

If you do not specify this parameter, the cmdlet uses the name of the entry point for the server on which you run  the cmdlet.
You can use the **ComputerName** parameter to specify the computer that runs the cmdlet.
If you specify both this parameter and the **ComputerName** parameter, and the computer that you specify in the **ComputerName** parameter is not the host of the site that you specify in this parameter, the cmdlet uses the site that you specify in this parameter.

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

### -Force
Forces the command to run without asking for user confirmation.

When suppressed the cmdlet assumes user confirmation for the following conditions.

 -- Uninstalling RA, after which users will not be able to connect remotely to corporate network.

 -- If NLS is on DA server, then uninstallation will lead to decommissioning of the NLS URL and clients that have not received updated policies will always be detected to be outside corporate network and will not be able to access corporate resources when inside corporate network.

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

### -VpnType
Specifies the type of VPN that should be uninstalled.
The acceptable values for this parameter are:

 -- Vpn.

 -- VpnS2S.

```yaml
Type: String
Parameter Sets: (All)
Aliases: RoleType
Accepted values: Vpn, VpnS2S

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### System.Object

## NOTES

## RELATED LINKS

[Get-RemoteAccess](./Get-RemoteAccess.md)

[Install-RemoteAccess](./Install-RemoteAccess.md)

[Remove-DAEntryPoint](./Remove-DAEntryPoint.md)

[Remove-RemoteAccessLoadBalancerNode](./Remove-RemoteAccessLoadBalancerNode.md)

[Set-RemoteAccess](./Set-RemoteAccess.md)

