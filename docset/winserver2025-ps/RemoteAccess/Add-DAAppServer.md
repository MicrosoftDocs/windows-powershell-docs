---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DAAppServer_v1.0.0.cdxml-help.xml
Module Name: RemoteAccess
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/remoteaccess/add-daappserver?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-DAAppServer
---

# Add-DAAppServer

## SYNOPSIS
Adds a new application server security group to the DirectAccess (DA) deployment, adds an application servers to an application server security group that is already part of the DirectAccess deployment, and adds or updates application server Group Policy Object (GPO) in a domain.

## SYNTAX

### AppServerSGGpo (Default)
```
Add-DAAppServer [-SecurityGroupNameList <String[]>] [-GpoName <String[]>] [-ComputerName <String>] [-PassThru]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### AppServerToSGGpo
```
Add-DAAppServer [-GpoName <String[]>] [-ComputerName <String>] [-PassThru] [-SecurityGroupName] <String>
 [-Name] <String[]> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Add-DAAppServer** cmdlet adds a new application server security group to the DirectAccess (DA) deployment, adds an application servers to an application server security group that is already part of the DirectAccess deployment, and adds or updates application server Group Policy Object (GPO) in a domain.
This cmdlet is not applicable when DA is deployed only for the management of remote clients.

The application server security group and GPO parameters are treated as independent entities.
The basic paradigm is that a user can create application server GPOs independent of the SGs and the domains where these SGs exist.
Every SG that is added to the DA deployment is added in all application server GPOs currently present.
Hence, all GPOs always contain all SGs even if all the corresponding domains are not represented in all the SGs.
There will never be a scenario where an SG is present only in some of the GPOs.
If this happens, then it means that the configuration is in a bad state.

With this paradigm there is still a need to parse the SG to add independent application servers in an SG because every application server has a unique end-to-end IPsec policy in all client and application server GPOs.

The following additional capabilities of the application server cmdlets justify their need though AD cmdlets are already available for the addition of SGs and GPOs.

 -- When an SG is added it is added in all GPOs.
Additionally, if the user does not have permissions to edit a GPO the SG is not added to any of the GPOs.
When using the AD cmdlet user would have to carefully ensure that it is run for each of the domains and it is difficult to handle the case where the user does not have permissions on some domains.

 -- When a GPO is added all SGs are added in the GPO and application server specific policies are created.
The cmdlet takes care of the conditions where the GPO is created if not already present.
If the GPO is already present then it is merely edited.

The App Server configuration is a global configuration and is applicable to all DA servers in the enterprise deployment even when there is multi-site enterprise deployment.

Following are additional behavioral notes for this cmdlet.

 -- If the user adds an SG without specifying a domain or GPO, then by default an application server GPO is created in the DA server's domain.
If the user specifies a GPO name or domain name, then the GPO is created only in that domain.

 -- Adding an application server GPO alone without any application server SGs is permitted operation.
When adding a GPO the admin can either specify the name of the GPO and the domain to which it belongs or the domain name alone.
If only a domain is specified, then the GPO is created with a default name.

 -- If nested SGs are specified, then the cmdlet recursively parses all SGs so that all servers are retrieved and policies can be created or removed accordingly.
However, the cmdlet does not refer to the domain to which an application server belongs.
Hence it is the responsibility of the user to ensure that application server GPOs are created in every supported domain by explicitly adding GPOs in that domain.

 -- When adding a new app server GPO if it is already present in the domain then it is merely configured with the SGs,IPsec policies and other settings.
If it is not present then it is created first.

 -- If user tries to re-add a GPO by either re-adding a domain or specifying the same GPO name for the domain again then no changes are made.

 - If the user tries to add a GPO with a new name in a domain that already contains an app server GPO, then no action is taken but a non-terminating error is displayed.
If this cmdlet finds that no action can be taken based on the parameters passed, then it will return a terminating error.

 -- When adding SGs if the user does not have the permissions to configure even one app server GPO among the many that might be present then the cmdlet terminates the processing of the entire list of SGs specified.
However, it still processes any GPOs that the user might have specified to add.

 -- When adding GPOs if the user does not have the permissions to create or configure one of the specified GPOs then the cmdlet still proceeds with the processing of the remaining GPOs in the list.

 -- Each new application server GPO that is added is configured with the end-to-end authentication and IPsec traffic protection settings.
These settings are common to all GPOs.
The default values assigned by this cmdlet for end-to-end authentication is E2EAuthOnlyToAppServer and IPsec traffic protection is Disabled The default setting is Enabled.
If the user wishes to change these values, then use the Set-DAAppServerConnection cmdlet.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Add-DAAppServer -SecurityGroupNameList daAppServerGrp -PassThru
SecurityGroupNameList: {corp.contoso.com\daappservergrp}
GpoName              : {corp.contoso.com\DirectAccess Application Server Settings}
ConnectionType       : E2EAuthOnlyToAppServer
TrafficProtection    : Enabled
```

This example adds an appserver security group to DirectAccess deployment.

This cmdlet adds security group daAppServerGrp consisting of application servers to the DirectAccess deployment.
Additionally, a GPO is created with default name DirectAccess Application Server Settings in the same domain as the DirectAccess server and the GPO is filtered on this security group.

### EXAMPLE 2
```
PS C:\>Add-DAAppServer -Name da-test-0807 -SecurityGroupName daAppServerGrp
SecurityGroupNameList: {corp.contoso.com\daappservergrp}
GpoName              : {corp.contoso.com\DirectAccess Application Server Settings}
ConnectionType       : E2EAuthOnlyToAppServer
TrafficProtection    : Enabled
```

This example add an application server to the application server security group.

This cmdlet adds the application server da-test-0807 to the pre-existing security group daappservergrp.

### EXAMPLE 3
```
PS C:\>Add-DAAppServer -GpoName child.corp.contoso.com\DAAppServerGpo -PassThru
SecurityGroupNameList: {corp.contoso.com\testappserver}
GpoName              : {corp.contoso.com\DirectAccess Application Server Settings,
                       child.corp.contoso.com\DAAppServerGpo}
ConnectionType       : E2EAuthOnlyToAppServer
TrafficProtection    : Enabled
```

This example adds an application server GPOs to the DirectAccess deployment.
The setup consists of two domains viz.
corp.contoso.com and child.corp.contoso.com.
There is already an Application Server GPO in corp.contoso.com.
This cmdlet adds a GPO in the domain child.corp.contoso.com

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
Specifies the IPv4 or IPv6 address, or host name, of the computer on which the remote access server computer specific tasks should be run.

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

### -GpoName
Specifies the name to be used when creating the application server GPO in the specified domain or represents the domain in which an app server GPO with the default name should be created.
GPO is specified in the format `DOMAIN\GPO_NAME`.
Domain is specified in the format `DOMAIN`.
If the parameter contains only the domain name then the following default GPO name is used:

 -- \<domain\> application server policy for \<DirectAccess connection friendly name\>.

The Default value is DirectAccess Application Server Settings

A list of GPOs can be specified.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the list of application servers that have to be added to the DirectAccess deployment.
The servers are specified by their hostnames and are added to the security group specified by the **SecurityGroupName** parameter.
The servers cannot be specified by their IPv4 or IPv6 addresses.

```yaml
Type: String[]
Parameter Sets: AppServerToSGGpo
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -SecurityGroupName
Specifies the name of a security group that is already part of the DirectAccess deployment to which the specified list of application servers should be added.
Specified in the `DOMAIN\SG_NAME` format.

```yaml
Type: String
Parameter Sets: AppServerToSGGpo
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SecurityGroupNameList
Specifies the list of application server security groups that are to be added to the DirectAccess deployment.
Specified in `DOMAIN\SG_NAME` format.

```yaml
Type: String[]
Parameter Sets: AppServerSGGpo
Aliases:

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

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#DAAppServer

The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

The DAAppServer object consists of the following properties:

 -- The list of application server security groups.
Each security group is specified in the `Domain\GroupName` format.

 -- The List of application server GPOs.
Each GPO is specified in the `Domain\GPOName` format.

 -- The properties of the connection to the application server.
If there are no application servers configured then the default value is NoE2EAuth, which mean no end-to-end authentication is required.

 -- Whether or not IPsec traffic protection is enabled.
If there are no application servers configured then the default value is Disabled.

## NOTES

## RELATED LINKS

[Get-DAAppServer](./Get-DAAppServer.md)

[Remove-DAAppServer](./Remove-DAAppServer.md)

[Set-DAAppServerConnection](./Set-DAAppServerConnection.md)

