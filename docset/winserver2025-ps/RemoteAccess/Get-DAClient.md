---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DAClient_v1.0.0.cdxml-help.xml
Module Name: RemoteAccess
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/remoteaccess/get-daclient?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DAClient
---

# Get-DAClient

## SYNOPSIS
Displays the list of client security groups that are part of the DirectAccess (DA) deployment and the client properties.

## SYNTAX

```
Get-DAClient [-ComputerName <String>] [[-EntrypointName] <String>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-DAClient** cmdlet displays the list of client security groups that are part of the DirectAccess (DA) deployment and the client properties.

The output displayed consists of the following.

 -- DA client properties, which are globally applicable to all clients, such as the status of force tunneling, suffix list in the Name Resolution Policy Table (NRPT) entry corresponding to force tunneling, status of policy to deploy DA only on laptops and notebooks and not on all of the computers in the domain, status of whether appropriate policies should be deployed on down level clients (firstref_client_7) clients such that they too can connect to the Windows Server® 2012 DA Server.

 -- Client Security Groups and Group Policy Objects (GPOs).

 -- If multi-site is deployed then the SGs and GPOs of down-level clients belonging to a site (such as clients that can connect to a site).
The **EntryPoint** parameter is used to specify the site.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Get-DAClient -EntryPointName 1-Edge-Site
SecurityGroupNameList  : {corp.contoso.com\DirectAccessClients}
GPOName    : {corp.contoso.com\DirectAccess Client Settings}
OnlyRemoteComputers   : Disabled
Downlevel    : Disabled
ForceTunnelingStatus  : Disabled
ForceTunnelingNrptSuffix  :
EntrypointName   : 1-Edge-Site
DownlevelSecurityGroupNameList :
DownlevelGpoName   :
```

This example retrieves DAClient properties applicable to all clients in the site 1-Edge-Site.
As can be seen from the output, the cmdlet lists down all the security groups currently configured for DA and the client GPO.
In addition, it gets status of force tunneling and whether DA is provisioned for Down level clients.
The OnlyRemoteComputers property refers to whether the WMI filter to provision DA only for remote laptops and notebooks is enabled.
The Downlevel property is not applicable in this case since it is a multi-site setup.

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
Specifies the IPv4 or IPv6 address, or host name, of the computer on which the Remote Access server computer specific tasks should be run.

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

### -EntrypointName
Specifies the identity of a site in a multi-site deployment.
When specified only those down-level security groups and GPOs that belong to the specified site (such as these clients connect only to this site) are displayed.
However, all Windows® 8 security groups and GPOs are displayed as they are independent of site.

If there is a multi-site deployment, then down-level client security group and GPO information is always retrieved only for a specific site.
If this parameter is not specified, then the site to which the computer on which the cmdlet is run is used (the user may or may not be specifying a computer name).
It is not possible to retrieve all the down-level security groups and GPOs across all sites.

If both this parameter and the **ComputerName** parameter are specified and the computer name does not belong to the site represented by the entry point, then this parameter takes precedence and the authentication type is configured for it.

If there is no multi-site deployment but user specifies this parameter, then the cmdlet returns an error message.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#DAClient

The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

The output object contains the following properties:

 -- The list of client security groups present in the DA deployment.

 -- The list of client GPOs present in the DA deployment.

 -- The status of force tunnel.

 -- The NRPT object (for force tunnel properties).

 -- The status of the policy to deploy DA only on laptops and notebooks and not on all of the computers in the domain.

 -- The status of whether appropriate policies should be deployed on down-level clients (Windows® 7) to enable the clients to connect to the Windows Server 2012 DA Server.

If multi-site is enabled, then the following additional properties are present:

 -- The name of the entry point (identity of a site) to which down-level clients are added.

 -- The name of the down-level client GPO.

 -- The list of security groups of down-level clients.

## NOTES

## RELATED LINKS

[Add-DAClient](./Add-DAClient.md)

[Remove-DAClient](./Remove-DAClient.md)

[Set-DAClient](./Set-DAClient.md)

