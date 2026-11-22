---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DAClient_v1.0.0.cdxml-help.xml
Module Name: RemoteAccess
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/remoteaccess/remove-daclient?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-DAClient
---

# Remove-DAClient

## SYNOPSIS
Removes one or more client computer security groups (SGs) from the DirectAccess (DA) deployment, removes one or more DA client Group Policy Objects (GPOs) from domains, removes one or more SGs of down-level clients (down-level clients can connect only to the specified site) from the DA deployment in a multi-site deployment, and removes one or more down-level DA client GPOs from domains in a multi-site deployment.

## SYNTAX

### ClientSGGpo (Default)
```
Remove-DAClient [-ComputerName <String>] [-PassThru] [-SecurityGroupNameList <String[]>]
 [-DomainName <String[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ClientDownlevelSGGpo
```
Remove-DAClient [-ComputerName <String>] [-PassThru] [-DownlevelSecurityGroupNameList <String[]>]
 [-EntrypointName <String>] [-DownlevelDomainName <String[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-DAClient** cmdlet removes one or more client computer security groups (SGs) from the DirectAccess (DA) deployment, removes one or more DA client Group Policy Objects (GPOs) from domains, removes one or more SGs of down-level clients (down-level clients can connect only to the specified site) from the DA deployment in a multi-site deployment, and removes one or more down-level DA client GPOs from domains in a multi-site deployment.

The basic paradigm is that all client GPOs always point to all SGs even if the domains to which these GPOs belong are not represented in the SGs.
There will never be a scenario where an SG is present only in some of the GPOs.
If this happens, then the state of the configuration is bad.
A user can remove client GPOs independent of the SGs and the domains these SGs represent.
Every SG that is removed from the DA deployment is removed in all client GPOs currently present.

When this paradigm is extended to clients being removed from an SG we see that it is a pure SG level operation which can be accomplished using Active Directory (AD) cmdlets (such as Remove-ADGroupMember).

Although AD cmdlets are already available for the removal of SGs and GPOs, the additional capabilities of this cmdlet are justified as follows.
- When an SG is removed it is removed in all GPOs.
If user does not have permissions to edit a GPO, then the SG is not removed from any of the domains.
When using the AD cmdlet, the user would have to carefully ensure that it is run for each of the domains and it is difficult to handle the case where the user does not have permissions on some domains.
 -- When a GPO is removed all SGs in the GPO are removed and DA client specific policies are deleted.
This cmdlet takes care of the conditions where the GPO is removed at the time of deletion.
If the GPO was already present when adding it to the DA deployment, then only the DA related policies and settings are deleted and the GPO is left intact.

The following are additional behavior notes for the cmdlet.
 -- The user is not allowed to delete all client GPOs and SGs.
At least one of each should be present always.
- Attempting to remove SGs in even a single GPO with the correct permissions results in the cmdlet terminating the processing of the entire list of SGs that were specified.
However, This cmdlet still processes the list of domains that the user might have specified in the cmdlet.
- Attempting to create, remove, or configure a client GPO in one of the specified domains without the correct permissions will result in a non-terminating error for that domain but the cmdlet proceeds with the processing of the remaining domains.

## EXAMPLES

### Example 1: Remove an SG from DA deployment
```
PS C:\> Remove-DAClient -SecurityGroupNameList "corp.contoso.com\DirectAccessMobileClients"
```

This command removes the DirectAccessMobileClients SG from the DA deployment.
The use of the cmdlet to restrict users and laptops in DirectAccessMobileClients SG from accessing the corporate resources of our Contoso firm is demonstrated here.

### Example 2: Display the deployment of a specific domain
```
PS C:\>Remove-DAClient -DomainName "child.corp.contoso.com"
```

This command displays the deployment that contains two domains viz.corp.contoso.com and child.corp.contoso.com and the cmdlet removes the DA client GPO in child.corp.contoso.com domain.
This cmdlet automatically locates the client GPO in the domain and removes it.

### Example 3: Remove DirectAccess for client computers in a specific domain
```
PS C:\>Remove-DAClient -DownLevelSecurityGroupNameList "child.corp.contoso.com\DownlevelClients" -DownlevelDomainName "child.corp.contoso.com" -EntrypointName "2-Edge-Site" -PassThru
SecurityGroupNameList  : {corp.contoso.com\DirectAccessLaptopClients}
GPOName    : {corp.contoso.com\DirectAccess Client Settings}
OnlyRemoteComputers   : Disabled
Downlevel    : Disabled
ForceTunnelingStatus  : Disabled
ForceTunnelingNrptSuffix  :
EntrypointName   :
DownlevelSecurityGroupNameList :
DownlevelGpoName   :
```

This command removes DA for firstref_client_7 client computers present in domain named child.corp.contoso.com at site 2-Edge-Site.
This is accomplished by removing the client SG DownlevelClients which contains the Windows® 7 clients and the domain named child.corp.contoso.com.

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

### -DomainName
Specifies the list of domains in which client GPOs need to be removed.
A domain is specified in the `DOMAIN` format.

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

### -DownlevelDomainName
Specifies the list of domains in which client GPOs need to be removed.
A domain is specified in the `DOMAIN` format.

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

### -DownlevelSecurityGroupNameList
Specifies the names of one or more down-level client SGs that are part of the DA deployment which need to be removed.
This parameter is specified in `DOMAIN\SG_NAME` format.

These down-level clients can connect only to the site specified in the *EntryPointName* parameter.

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
Specifies the identity of a site in a multi-site deployment from which down-level clients are removed (these clients can only connect to the specified site).
If this parameter is not specified, then the site to which the computer on which the cmdlet is run is used (the *ComputerName* parameter may or may not be specified).
If both this parameter and the *ComputerName* parameter are specified and the computer name does not belong to the site represented by the entry point name then this parameter takes precedence and the authentication type is configured for it.

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
Specifies a list of client SGs that are part of the DA deployment which need to be removed.
The name of the SG is in `DOMAIN\SG_NAME` format.

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
The DAClient object contains the following properties:
- The list of client security groups present in the DA deployment.
- The list of client GPOs present in the DA deployment.
- The status of force tunnel.
- The NRPT object (for force tunnel properties).
- The status of the policy to deploy DA only on laptops and notebooks and not on all of the computers in the domain.
- The status of whether appropriate policies should be deployed on down-level clients (Windows® 7) to enable them to connect to the Windows Server 2012 DA Server.
If multi-site is enabled, then the following additional properties are present:
- The name of the entry point (identity of a site) to which down-level clients are added.
- The name of the down-level client GPO.
- The list of security groups of down-level clients.

## NOTES

## RELATED LINKS

[Add-DAClient](./Add-DAClient.md)

[Get-DAClient](./Get-DAClient.md)

[Set-DAClient](./Set-DAClient.md)

