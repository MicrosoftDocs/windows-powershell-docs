---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DAClient_v1.0.0.cdxml-help.xml
Module Name: RemoteAccess
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/remoteaccess/add-daclient?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-DAClient
---

# Add-DAClient

## SYNOPSIS
Adds one or more client computer security groups (SGs) to the DirectAccess (DA) deployment, adds one or more DA client Group Policy Objects (GPOs) in one or more domains, adds one or more SGs of down-level clients to the DA deployment in a multi-site deployment, or adds one or more down-level DA client GPOs in one or more domains in a multi-site deployment.

## SYNTAX

### ClientSGGpo (Default)
```
Add-DAClient [-ComputerName <String>] [-PassThru] [-SecurityGroupNameList <String[]>] [-GpoName <String[]>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ClientDownlevelSGGpo
```
Add-DAClient [-DownlevelGpoName <String[]>] [-DownlevelSecurityGroupNameList <String[]>]
 [-EntrypointName <String>] [-ComputerName <String>] [-PassThru] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-DAClient** cmdlet adds one or more client computer security groups (SGs) to the DirectAccess (DA) deployment, adds one or more DA client Group Policy Objects (GPOs) in one or more domains, adds one or more SGs of down-level clients to the DA deployment in a multi-site deployment, or adds one or more down-level DA client GPOs in one or more domains in a multi-site deployment.

The client SG and GPO parameters are treated as independent entities.
The basic paradigm is that client GPOs can be created independent of the SGs and the represented domains.
Every SG that is added to the DA deployment is added in all current client GPOs.
Therefore all GPOs always contain all SGs even if all the corresponding domains are not represented in all the SGs.

There will never be a scenario where an SG is present only in some of the GPOs.
If this happens, then it means that the state of the configuration is bad.

Extending this paradigm, adding clients to an SG is a pure SG level operation which can be accomplished using AD cmdlets, such as the Add-ADGroupMember cmdlet.

Although AD cmdlets are already available for the addition of SGs and GPOs, the additional capabilities of this cmdlet are justified as follows.

 -- When an SG is added it is added in all Client GPOs.
If user does not have permissions to edit a GPO, then the SG is not added to any of the Client GPOs in any of the domains.
When using the AD cmdlet, the user would have to carefully ensure that it is run for each of the domains and it is difficult to handle the case where the user does not have permissions on some domains.

 -- When a GPO is added all SGs are added in the GPO and DA client specific policies are created.
This cmdlet takes care of the conditions where the GPO is created if not already present.
If the GPO is already present, then it is merely edited

The following are additional behavior notes for the cmdlet.

 -- At least one client GPO is always present.
The Install-RemoteAccess cmdlet always creates a GPO even if there are no SGs added.
There is never a case where there are no client GPOs.
However, if this situation occurs, then adding an SG without specifying a domain or GPO is not allowed.
A GPO can still be added alone, but only when there is no client GPO already present in that domain.

 -- If DA is configured to be deployed only on laptops and notebooks, then when a domain or GPO is added, a WMI filter to enforce this policy is created in that domain and applied to all the SGs.
If the user does not have the permissions to create a filter in a domain, then a GPO is not created in that domain and a non-terminating error is issued.

 -- When adding a new GPO, if it is already present in the domain, then it is merely configured with the list of SG and DA client specific policies.
Essentially, it is brought into the DA deployment.
If it is not present, then it is created first.

 -- Attempting to re-add a domain or specify the same GPO name for the domain again will result in no changes being made.

 -- Attempting to add a new GPO in a domain that already consists of a client GPO will result in no action being taken and the display of a non-terminating error.

 -- Attempting to add SGs in even a single GPO without the correct permissions will result in the cmdlet terminating the processing of the entire list of SGs that were specified.
However, the cmdlet still processes the list of GPOs that have been specified.

 -- Attempting to create or configure one of the specified GPOs without the correct permissions will result in the cmdlet proceeding with the processing of the remaining GPOs.

 -- In a multi-site deployment.

 ---- Clients that are added can connect to all the sites.

 ---- A separate set of parameters is available for adding down-level clients.
Additional information can be found under parameter description.

 -- If multi-site has not been deployed, attempting to add down-level GPOs or SGs using the **DownlevelGpoName** and **DownlevelSecurityGroupNameList** parameters will display an error.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Add-DAClient -SecurityGroupNameList 'corp.contoso.com\DirectAccessLaptopClients','corp.contoso.com\DirectAccessMobileClients' -PassThru
SecurityGroupNameList          : {corp.contoso.com\DirectAccessLaptopClients, corp.contoso.com\DirectAccessMobileClients}
GPOName                        : {corp.contoso.com\DirectAccess Client Settings}
OnlyRemoteComputers            : Disabled
Downlevel                      : Disabled
ForceTunnelingStatus           : Disabled
ForceTunnelingNrptSuffix       :
EntrypointName                 :
DownlevelSecurityGroupNameList :
DownlevelGpoName               :
```

This example will add the SGs corp.contoso.com\DirectAccessLaptopClients and corp.contoso.com\DirectAccessMobileClients to DA configuration.
corp .contoso.com/DirectAccess Client Settings is the DA Client GPO configured at the time of DA installation.

Two new SGs DirectAccessLaptopClients and DirectAccessMobileClients are created and DA Connectivity is provisioned for these SGs.
This cmdlet will add the SGs to DA configuration.
This essentially means that the existing Client GPO configuration corp.contoso.com/DirectAccess Client Settings will be filtered on the two SGs.

This cmdlet will only provision Windows® 8 clients.
Down-level clients have to be provisioned separately.

### EXAMPLE 2
```
PS C:\>Add-DAClient -GPOName 'child.corp.contoso.com' -PassThru
SecurityGroupNameList          : {corp.contoso.com\DirectAccessLaptopClients, corp.contoso.com\DirectAccessMobileClients}
GPOName                        : {corp.contoso.com\DirectAccess Client Settings, child.corp.contoso.com\DirectAccess Client Settings}
OnlyRemoteComputers            : Disabled
Downlevel                      : Disabled
ForceTunnelingStatus           : Disabled
ForceTunnelingNrptSuffix       :
EntrypointName                 :
DownlevelSecurityGroupNameList :
DownlevelGpoName               :
```

This example will provision DA for the domain child.corp.contoso.com which is the child of corp.contoso.com.
This will create a GPO named child.corp.contoso.com/DirectAccess Client Settings, using default naming convention).
This cmdlet makes sure that all the SGs present in DA Client configuration are added to this GPO.

### EXAMPLE 3
```
PS C:\>Add-DAClient -DownlevelSecurityGroupNameList 'child.corp.contoso.com\DownlevelClients' -DownlevelGPOName 'child.corp.contoso.com\DownLevelClientsGPO' -EntrypointName '2-Edge-Site' -PassThru
SecurityGroupNameList          : {corp.contoso.com\DirectAccessLaptopClients, corp.contoso.com\DirectAccessMobileClients}
GPOName                        : {corp.contoso.com\DirectAccess Client Settings, child.corp.contoso.com\DirectAccess Client Settings }
OnlyRemoteComputers            : Disabled
Downlevel                      : Disabled
ForceTunnelingStatus           : Disabled
ForceTunnelingNrptSuffix       :
EntrypointName                 :
DownlevelSecurityGroupNameList : child.corp.contoso.com\DownlevelClients
DownlevelGpoName               : child.corp.contoso.com\DownLevelClientsGPO
```

This example provisions DA for firstref_client_7 clients present in the domain child.corp.contoso.com enabling them to connect to site 2-Edge-Site.
2-Edge-Site is the site configured for the child domain.
A new GPO (**DownlevelClientsGPO**) can be added to the DirectAccessConfiguration.
This GPO is filtered on DownlevelClients SG which contains Windows® 7 clients in the child domain.
Note: The Windows® 7 clients can only connect access the site specified in the **EntrypointName** parameter.

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

### -DownlevelGpoName
Specifies the name to be used when creating the down-level client GPO in the specified domain or represents the domain in which a down-level client GPO with the default name should be created.
GPO is specified in the format `DOMAIN\GPO_NAME`.
Domain is specified in the format `DOMAIN`.
This parameter can be used to create the multiple GPOs in multiple domains in one run, so the list of names of the GPOs can be provided.
These GPOs correspond to the down-level SGs added using the **DownlevelSecurityGroupNameList** parameter.

If this parameter contains only the domain name, then the following default GPO name is used.

 -- \<domain\> client policy for \<DirectAccess connection friendly name\>-\<entry point name\>.

A list of GPOs can be specified.

This parameter is applicable only in case of multi-site deployment.

```yaml
Type: String[]
Parameter Sets: ClientDownlevelSGGpo
Aliases: DownlevelGpoNameList

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DownlevelSecurityGroupNameList
Specifies the names of one or more down-level client SGs that are not already part of the DA deployment.
Specified in `DOMAIN\SG_NAME` format.

These down-level clients can then connect only to the site specified in the **EntrypointName** parameter.

This parameter is only applicable in case of a multi-site deployment.

```yaml
Type: String[]
Parameter Sets: ClientDownlevelSGGpo
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EntrypointName
Specifies the identity of a site in a multi-site deployment to which down-level clients are added, such as these clients can only connect to the specified site.
If this parameter is not specified, then the site to which the computer on which the cmdlet is run is used (the user may or may not be specifying a computer name).
If both this parameter and the **ComputerName** parameter are specified and the computer name does not belong to the site represented by the name of the entry point, then the entry point takes precedence and the authentication type is configured for it.

```yaml
Type: String
Parameter Sets: ClientDownlevelSGGpo
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -GpoName
Specifies the name to be used when creating the client GPO in the specified domain or represents the domain in which a client GPO with the default name should be created.
GPO is specified in the format `DOMAIN\GPO_NAME`.
Domain is specified in the format `DOMAIN`.
If this parameter contains only the domain name, then the following default GPO name is used.

 -- \<domain\> client policy for \<DirectAccess connection friendly name\>.

A list of GPOs can be specified.

```yaml
Type: String[]
Parameter Sets: ClientSGGpo
Aliases:

Required: False
Position: Named
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

### -SecurityGroupNameList
Specifies the list of client SGs that are to be added to the DA deployment.
Each SG is specified in `DOMAIN\SG_NAME` format.

```yaml
Type: String[]
Parameter Sets: ClientSGGpo
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

### Microsoft.Management.Infrastructure.CimInstance#DAClient

The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

The output object contains the following properties:

 -- The list of client SGs present in the DA deployment.

 -- The list of client GPOs present in the DA deployment.

 -- The status of force tunnel.

 -- The Name Resolution Policy Table (NRPT) object (for force tunnel properties).

 -- The status of the policy to deploy DA only on laptops and notebooks and not on all computers in the domain.

 -- The status of whether appropriate policies should be deployed on down-level clients (Windows® 7) to enable them to connect to the Windows Server 2012 DA server.

If multi-site is enabled, then the following additional properties are present:

 -- The name of the entry point (identity of a site) to which down-level clients are added.

 -- The name of the down-level client GPO.

 -- The list of SGs of down-level clients.

## NOTES

## RELATED LINKS

[Get-DAClient](./Get-DAClient.md)

[Remove-DAClient](./Remove-DAClient.md)

[Set-DAClient](./Set-DAClient.md)

