---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: NetIPsecMainModeCryptoSet.cmdletDefinition.cdxml-help.xml
Module Name: NetSecurity
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/netsecurity/rename-netipsecmainmodecryptoset?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Rename-NetIPsecMainModeCryptoSet
---

# Rename-NetIPsecMainModeCryptoSet

## SYNOPSIS
Renames a single main mode cryptographic set.

## SYNTAX

### GetAll (Default)
```
Rename-NetIPsecMainModeCryptoSet [-All] [-PolicyStore <String>] [-GPOSession <String>] [-TracePolicyStore]
 -NewName <String> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### ByName
```
Rename-NetIPsecMainModeCryptoSet [-Name] <String[]> [-PolicyStore <String>] [-GPOSession <String>]
 [-TracePolicyStore] -NewName <String> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByDisplayName
```
Rename-NetIPsecMainModeCryptoSet -DisplayName <String[]> [-PolicyStore <String>] [-GPOSession <String>]
 [-TracePolicyStore] -NewName <String> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByQuery
```
Rename-NetIPsecMainModeCryptoSet [-Description <String[]>] [-DisplayGroup <String[]>] [-Group <String[]>]
 [-MaxMinutes <UInt32[]>] [-MaxSessions <UInt32[]>] [-ForceDiffieHellman <Boolean[]>]
 [-PrimaryStatus <PrimaryStatus[]>] [-Status <String[]>] [-PolicyStoreSource <String[]>]
 [-PolicyStoreSourceType <PolicyStoreType[]>] [-PolicyStore <String>] [-GPOSession <String>]
 [-TracePolicyStore] -NewName <String> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByAssociatedNetIPsecMainModeRule
```
Rename-NetIPsecMainModeCryptoSet -AssociatedNetIPsecMainModeRule <CimInstance> [-PolicyStore <String>]
 [-GPOSession <String>] [-TracePolicyStore] -NewName <String> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject (cdxml)
```
Rename-NetIPsecMainModeCryptoSet -InputObject <CimInstance[]> -NewName <String> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Rename-NetIPsecMainModeCryptoSet** cmdlet renames an existing main mode cryptographic set.
When creating a set, if the *Name* parameter is not specified, then a randomly generated value is used.
This cmdlet allows the user to specify a friendly and descriptive set name.
The *NewName* parameter value must be unique since it identifies a single set object on the computer.

This cmdlet gets one or more main mode cryptographic sets to be renamed with the *Name* parameter (default), the *DisplayName* parameter, set properties, or by the associated filters or objects.
The *Name* parameter for the resulting queried set is replaced by the *NewName* parameter value.
Only one set can be renamed at a time when copying to the same policy store.
This is because only a single set can use the unique identifier, or name, specified by the *NewName* parameter.

To modify the localized *DisplayName* parameter, run the Set-NetIPsecMainModeCryptoSet cmdlet with the *NewDisplayName* parameter.

The names are unique identifiers for rules, similar to file names.
Each name must be unique within a given policy store.
If rules in multiple GPOs have the same name, then one will overwrite the other based upon GPO precedence.
If a rule from a GPO has the same name as a rule from the PersistentStore, then the rule from the GPO will overwrite the local rule.

To specify a new default main mode cryptographic set, run this cmdlet to specify the default set with the *Name* parameter value set to {E5A5D32A-4BCE-4e4d-B07F-4AB1BA7E5FE1}.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Rename-NetIPsecMainModeCryptoSet -Name "{ed8384a9-a78b-4d0d-8f3d-eb5615edb4a0}" -NewName "(DA Client) - Phase 2 Crypto Set"
```

This example renames a main mode cryptographic set so that the unique identifier is descriptive and user friendly.

## PARAMETERS

### -All
Indicates that all of the main mode cryptographic sets within the specified policy store are renamed.

```yaml
Type: SwitchParameter
Parameter Sets: GetAll
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -AssociatedNetIPsecMainModeRule
Gets the main mode cryptographic sets that are associated, via the pipeline, with the input main mode rule to be renamed.
This parameter represents a main mode rule, which alters the behavior of main mode authentications.
Main mode negotiation establishes a secure channel between two computers by determining a set of cryptographic protection suites, exchanging keying material to establish a shared secret key, and authenticating computer and user identities.
See the Get-NetIPsecMainModeRule cmdlet for more information.

```yaml
Type: CimInstance
Parameter Sets: ByAssociatedNetIPsecMainModeRule
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### -Description
Specifies that matching main mode cryptographic sets of the indicated description are renamed.
Wildcard characters are accepted.
This parameter provides information about the main mode cryptographic sets.
This parameter specifies a localized, user-facing description of the object.

```yaml
Type: String[]
Parameter Sets: ByQuery
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisplayGroup
Specifies that only matching main mode cryptographic sets of the indicated group association are renamed.
Wildcard characters are accepted.
The *Group* parameter specifies the source string for this parameter.
If the value for this parameter is a localizable string, then the *Group* parameter contains an indirect string.
Rule groups can be used to organize rules by influence and allows batch rule modifications.
Using the Set-NetIPsecMainModeCryptoSet cmdlet, if the group name is specified for a set of rules or sets, then all of the rules or sets in that group receive the same set of modifications.
It is good practice to specify the *Group* parameter with a universal and world-ready indirect @FirewallAPI name.
This parameter cannot be specified upon object creation using the New-NetIPsecMainModeCryptoSet cmdlet, but can be modified using dot notation and the Set-NetIPsecMainModeCryptoSet cmdlet.

```yaml
Type: String[]
Parameter Sets: ByQuery
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisplayName
Specifies that only matching main mode cryptographic sets of the indicated display name are renamed.
Wildcard characters are accepted.
This parameter specifies the localized, user-facing name of a single main mode cryptographic sets.
When creating a set this parameter is required.
This parameter value is locale-dependent.
If the object is not modified, this parameter value may change in certain circumstances.
When writing resilient scripts, the *Name* parameter should be used instead, where the default value is a randomly assigned value.
This parameter value cannot be All.

```yaml
Type: String[]
Parameter Sets: ByDisplayName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ForceDiffieHellman
Indicates that matching main mode cryptographic sets of the indicated value are renamed.
If this parameter is set to True, then IPsec uses Diffie-Hellman exchanges to protect the main mode key exchange when AuthIP is used.
AuthIP is specified by KeyModule.
This provides stronger security for the key exchange.
The default value is False.

```yaml
Type: Boolean[]
Parameter Sets: ByQuery
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GPOSession
Targets the network GPO from which to retrieve the sets to be renamed.
This parameter is used in the same way as the *PolicyStore* parameter.
When modifying Group Policy Objects (GPOs) in Windows PowerShell®, each change to a GPO requires the entire GPO to be loaded, modified, and saved back.
On a busy Domain Controller (DC), this can be a slow and resource-heavy operation.
A GPO Session loads a domain GPO onto the local computer and makes all changes in a batch, before saving it back.
This reduces the load on the DC and speeds up the Windows PowerShell cmdlets.
To load a GPO Session, use the Open-NetGPO cmdlet.
To save a GPO Session, use the Save-NetGPO cmdlet.

```yaml
Type: String
Parameter Sets: GetAll, ByName, ByDisplayName, ByQuery, ByAssociatedNetIPsecMainModeRule
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Group
Specifies that only matching main mode cryptographic sets of the indicated group association are renamed.
Wildcard characters are accepted.
This parameter specifies the source string for the *DisplayGroup* parameter.
If the *DisplayGroup* parameter value is a localizable string, then this parameter contains an indirect string.
Rule groups organize rules by influence and allows batch rule modifications.
Using the Set-NetIPsecMainModeCryptoSet cmdlet, if the group name is specified for a set of rules or sets, then all of the rules or sets in that group receive the same set of modifications.
It is good practice to specify this parameter with a universal and world-ready indirect @FirewallAPI name.
The *DisplayGroup* parameter cannot be specified upon object creation using the New-NetIPsecMainModeCryptoSet cmdlet, but can be modified using dot notation and the Set-NetIPsecMainModeCryptoSet cmdlet.

```yaml
Type: String[]
Parameter Sets: ByQuery
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the input object that is used in a pipeline command.

```yaml
Type: CimInstance[]
Parameter Sets: InputObject (cdxml)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -MaxMinutes
Specifies that matching main mode cryptographic sets of the indicated maximum lifetime, in minutes, are renamed.
This parameter specifies the number of minutes established for a main mode security association before it expires and must be renegotiated.
The acceptable values for this parameter are: 0 through 2879.

- A non-zero value specifies the desired minute lifetime.
- NotConfigured: Valid only when configuring a GPO.
Removes the setting from the GPO, which results in the policy not changing the value on the computer when the policy is applied.

The default value is 4800 minutes (eight hours).
When managing a GPO, the default setting is NotConfigured.

```yaml
Type: UInt32[]
Parameter Sets: ByQuery
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxSessions
Specifies that matching main mode cryptographic sets of the indicated maximum lifetime, in sessions, are renamed.
This parameter specifies the number of sessions established for a main mode security association before it expires and must be renegotiated.
The acceptable values for this parameter are: 0 through 2147483647.

- A value of zero (0) specifies that there should be no maximum session lifetime.
- A non-zero value specifies the desired session number.
- NotConfigured: Valid only when configuring a GPO.
Removes the setting from the GPO, which results in the policy not changing the value on the computer when the policy is applied.

The default value is zero (0) sessions.
When managing a GPO, the default setting is NotConfigured.

```yaml
Type: UInt32[]
Parameter Sets: ByQuery
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies that only matching main mode cryptographic sets of the indicated name are renamed.
Wildcard characters are accepted.
This parameter acts just like a file name, in that only one rule with a given name may exist in a policy store at a time.
During group policy processing and policy merge, rules that have the same name but come from multiple stores being merged, will overwrite one another so that only one exists.
This overwriting behavior is desirable if the rules serve the same purpose.
For instance, all of the firewall rules have specific names, so if an administrator can copy these rules to a GPO, and the rules will override the local versions on a local computer.
GPOs can have precedence.
So, if an administrator has a different or more specific rule the same name in a higher-precedence GPO, then it overrides other rules that exist.
The default value is a randomly assigned value.
When you want to override the defaults for main mode encryption, specify the customized parameters and set this parameter, making this parameter the new default setting for encryption.

```yaml
Type: String[]
Parameter Sets: ByName
Aliases: ID

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NewName
Specifies the new name for one or more main mode cryptographic sets.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
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

### -PolicyStore
Specifies the policy store from which to retrieve the sets to be renamed.
A policy store is a container for firewall and IPsec policy.
The acceptable values for this parameter are:
- PersistentStore: Sometimes called static rules, this store contains the persistent policy for the local computer.
This policy is not from GPOs, and has been created manually or programmatically, during application installation, on the computer.
Rules created in this store are attached to the ActiveStore and activated on the computer immediately.
- ActiveStore: This store contains the currently active policy, which is the sum of all policy stores that apply to the computer.
This is the resultant set of policy (RSOP) for the local computer (the sum of all GPOs that apply to the computer), and the local stores (the PersistentStore, the Static Windows Service Hardening (WSH), and the Configurable WSH).
---- GPOs are also policy stores.
Computer GPOs can be specified as follows.
------ `-PolicyStore hostname`.
---- Active Directory GPOs can be specified as follows.
------ `-PolicyStore domain.fqdn.com\GPO_Friendly_Namedomain.fqdn.comGPO_Friendly_Name`.
------ Such as the following.
-------- `-PolicyStore localhost`
-------- `-PolicyStore corp.contoso.com\FirewallPolicy`
---- Active Directory GPOs can be created using the **New-GPO** cmdlet or the Group Policy Management Console.
- RSOP: This read-only store contains the sum of all GPOs applied to the local computer.
- SystemDefaults: This read-only store contains the default state of firewall rules that ship with Windows Server® 2012.
- StaticServiceStore: This read-only store contains all the service restrictions that ship with Windows Server 2012.
Optional and product-dependent features are considered part of Windows Server 2012 for the purposes of WFAS.
- ConfigurableServiceStore: This read-write store contains all the service restrictions that are added for third-party services.
In addition, network isolation rules that are created for Windows Store application containers will appear in this policy store.
The default value is PersistentStore.
The Set-NetIPsecMainModeCryptoSet cmdlet cannot be used to add an object to a policy store.
An object can only be added to a policy store at creation time with Copy-NetIPsecMainModeCryptoSet or with the New-NetIPsecMainModeCryptoSet cmdlet.

```yaml
Type: String
Parameter Sets: GetAll, ByName, ByDisplayName, ByQuery, ByAssociatedNetIPsecMainModeRule
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PolicyStoreSource
Specifies that the main mode cryptographic sets that match the indicated policy store source are renamed.
This parameter contains a path to the policy store where the rule originated if the object is retrieved from the ActiveStore with the TracePolicyStoreSource option set.
This parameter value is automatically generated and should not be modified.
The monitoring output from this parameter is not completely compatible with the *PolicyStore* parameter.
This parameter value cannot always be passed into the *PolicyStore* parameter.
Domain GPOs are one example in which this parameter contains only the GPO name, not the domain name.

```yaml
Type: String[]
Parameter Sets: ByQuery
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PolicyStoreSourceType
Specifies that the main mode cryptographic sets that match the indicated policy store source type are renamed.
This parameter describes the type of policy store where the rule originated if the object is retrieved from the ActiveStore with the TracePolicyStoreSource option set.
This parameter value is automatically generated and should not be modified.
The acceptable values for this parameter are:

- Local: The object originates from the local store.
- GroupPolicy: The object originates from a GPO.
- Dynamic: The object originates from the local runtime state.
This policy store name is not valid for use in the cmdlets, but may appear when monitoring active policy.
- Generated: The object was generated automatically.
This policy store name is not valid for use in the cmdlets, but may appear when monitoring active policy.
- Hardcoded: The object was hard-coded.
This policy store name is not valid for use in the cmdlets, but may appear when monitoring active policy.

```yaml
Type: PolicyStoreType[]
Parameter Sets: ByQuery
Aliases:
Accepted values: None, Local, GroupPolicy, Dynamic, Generated, Hardcoded

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrimaryStatus
Specifies that the main mode cryptographic sets that match the indicated primary status are renamed.
This parameter describes the overall status of the rule.
- OK: Specifies that the rule will work as specified.
- Degraded: Specifies that one or more parts of the rule will not be enforced.
- Error: Specifies that the computer is unable to use the rule at all.
See the Status and StatusCode fields of the object for more detailed status information.

```yaml
Type: PrimaryStatus[]
Parameter Sets: ByQuery
Aliases:
Accepted values: Unknown, OK, Inactive, Error

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Status
Specifies that the main mode cryptographic sets that match the indicated status are renamed.
This parameter describes the status message for the specified status code value.
The status code is a numerical value that indicates any syntax, parsing, or runtime errors in the rule.
This parameter value should not be modified.

```yaml
Type: String[]
Parameter Sets: ByQuery
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

### -TracePolicyStore
Indicates that the main mode cryptographic sets that match the indicated policy store are renamed.
This parameter specifies that the name of the source GPO is queried and set to the *PolicyStoreSource* parameter value.

```yaml
Type: SwitchParameter
Parameter Sets: GetAll, ByName, ByDisplayName, ByQuery, ByAssociatedNetIPsecMainModeRule
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

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\AssociatedNetIPsecMainModeCryptoSet[]
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_NetMainModeRule[]
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Copy-NetIPsecMainModeCryptoSet](./Copy-NetIPsecMainModeCryptoSet.md)

[Get-NetIPsecMainModeRule](./Get-NetIPsecMainModeRule.md)

[New-NetIPsecMainModeCryptoSet](./New-NetIPsecMainModeCryptoSet.md)

[Set-NetIPsecMainModeCryptoSet](./Set-NetIPsecMainModeCryptoSet.md)

