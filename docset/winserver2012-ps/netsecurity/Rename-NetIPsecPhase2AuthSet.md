---
external help file: NetSecurity_Function.xml
Module Name: NetSecurity
online version: https://learn.microsoft.com/powershell/module/netsecurity/rename-netipsecphase2authset?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Rename-NetIPsecPhase2AuthSet

## SYNOPSIS
Renames a single phase 2 authentication set.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Rename-NetIPsecPhase2AuthSet [-All] [-AsJob] [-CimSession <CimSession[]>] [-GPOSession <String>] [-PassThru]
 [-PolicyStore <String>] [-ThrottleLimit <Int32>] [-TracePolicyStore] -NewName <String> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Rename-NetIPsecPhase2AuthSet [-Name] <String[]> [-AsJob] [-CimSession <CimSession[]>] [-GPOSession <String>]
 [-PassThru] [-PolicyStore <String>] [-ThrottleLimit <Int32>] [-TracePolicyStore] -NewName <String> [-Confirm]
 [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Rename-NetIPsecPhase2AuthSet [-AsJob] [-CimSession <CimSession[]>] [-PassThru] [-ThrottleLimit <Int32>]
 -InputObject <CimInstance[]> -NewName <String> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_4
```
Rename-NetIPsecPhase2AuthSet [-AsJob] [-CimSession <CimSession[]>] [-GPOSession <String>] [-PassThru]
 [-PolicyStore <String>] [-ThrottleLimit <Int32>] [-TracePolicyStore] -AssociatedNetIPsecRule <CimInstance>
 -NewName <String> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_5
```
Rename-NetIPsecPhase2AuthSet [-AsJob] [-CimSession <CimSession[]>] [-Description <String[]>]
 [-DisplayGroup <String[]>] [-GPOSession <String>] [-Group <String[]>] [-PassThru] [-PolicyStore <String>]
 [-PolicyStoreSource <String[]>] [-PolicyStoreSourceType <PolicyStoreType[]>]
 [-PrimaryStatus <PrimaryStatus[]>] [-Status <String[]>] [-ThrottleLimit <Int32>] [-TracePolicyStore]
 -NewName <String> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_6
```
Rename-NetIPsecPhase2AuthSet [-AsJob] [-CimSession <CimSession[]>] [-GPOSession <String>] [-PassThru]
 [-PolicyStore <String>] [-ThrottleLimit <Int32>] [-TracePolicyStore] -DisplayName <String[]> -NewName <String>
 [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Rename-NetIPsecPhase2AuthSet** cmdlet renames an existing phase 2 authentication set.
When creating a set, if the **Name** parameter is not specified, then a random GUID is used.
This cmdlet specifies a friendly and descriptive rule name.
Note: The newly specified name, using the **NewName** parameter must still be unique since it identifies a single rule object on the computer.

This cmdlet gets one or more phase 2 authentication sets to be renamed with the **Name** parameter (default), the **DisplayName** parameter, set properties, or by associated filters or objects.
The **Name** parameter value from the queried set is replaced by the **NewName** parameter value.
Note: Only one set can be renamed at a time when copying to the same policy store.
This is because only a single set can use the unique identifier, or name, specified by the **NewName** parameter.

To modify the localized **DisplayName** parameter, run the Set-NetIPsecPhase2AuthSet cmdlet with the **NewDisplayName** parameter.

The names are unique identifiers for rules, similar to file names.
Each name must be unique within a given policystore.
If the rules in multiple GPOs have the same name, then one will overwrite the other based upon GPO precedence.
If a rule from a GPO has the same name as a rule from the PersistentStore, then the rule from the GPO will overwrite the local rule.

To specify a new default phase 2 authentication set, run the Set-NetIPsecPhase2AuthSet to specify the default set with the **Name** parameter value {E5A5D32A-4BCE-4e4d-B07F-4AB1BA7E5FE1}.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Rename-NetIPsecPhase2AuthSet -Name "{ed8384a9-a78b-4d0d-8f3d-eb5615edb4a0}" -NewName "Transport Mode - Extranet IPv4 - Phase 2 Auth Set"
```

This example renames a phase 2 authorization set so that the unique identifier is descriptive and user friendly.

## PARAMETERS

### -All
Indicates that all of the phase 2 authentication sets within the specified policy store are renamed.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AsJob
ps_cimcommon_asjob

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

### -AssociatedNetIPsecRule
Gets the phase 2 authentication sets that are associated, via the pipeline, with the input IPsec rule to be renamed. 

A NetIPsecRule object represents an IPsec rule, which determines IPsec behavior.
An IPsec rule can be associated with Phase1AuthSet, Phase2AuthSet, and NetIPsecQuickMode cryptographic sets.
See the New-NetIPsecMainModeRule cmdlet for more information.

```yaml
Type: CimInstance
Parameter Sets: UNNAMED_PARAMETER_SET_4
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a New-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
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

### -Description
Indicates that matching phase 2 authentication sets of the indicated description are copied.
Wildcard characters are accepted. 

This parameter provides information about the phase 2 authentication rule.
This parameter specifies a localized, user-facing description of the object.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_5
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisplayGroup
Indicates that only matching phase 2 authentication sets of the indicated group association are renamed.
Wildcard characters are accepted. 

The **Group** parameter specifies the source string for this parameter.
If the value for this parameter is a localizable string, then the **Group** parameter contains an indirect string.
Rule groups can be used to organize rules by influence and allows batch rule modifications.
Using the Set-NetIPsecPhase2AuthSet cmdlet, if the group name is specified for a set of rules, then all of the rules in that group receive the same set of modifications.
It is good practice to specify the **Group** parameter with a universal  and world-ready indirect @FirewallAPI name. 
Note: This parameter cannot be specified upon object creation using the New-NetIPsecPhase2AuthSet cmdlet, but can be modified using dot notation and the Set-NetIPsecPhase2AuthSet cmdlet.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_5
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisplayName
Indicates that only matching phase 2 authentication sets of the indicated display name are renamed.
Wildcard characters are accepted. 

This parameter specifies the localized, user-facing name of the phase 2 authentication set being created.
When creating a set this parameter is required.
This parameter value is locale-dependent.
If the object is not modified, this parameter value may change in certain circumstances.
When writing scripts in multi-lingual environments, the **Name** parameter should be used instead, where the default value is a randomly assigned value. 
Note: This parameter value cannot be All.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_6
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GPOSession
Targets the network GPO from which to retrieve the sets to be renamed. 

This parameter is used in the same way as the **PolicyStore** parameter.
When modifying Group Policy objects (GPOs) in Windows PowerShell®, each change to a GPO requires the entire GPO to be loaded, modified, and saved back.
On a busy Domain Controller (DC), this can be a slow and resource-heavy operation.
A GPO Session loads a domain GPO onto the local computer and makes all changes in a batch, before saving it back.
This reduces the load on the DC and speeds up the Windows PowerShell cmdlets.
To load a GPO Session, use the Open-NetGPO cmdlet.
To save a GPO Session, use the Save-NetGPO cmdlet.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_4, UNNAMED_PARAMETER_SET_5, UNNAMED_PARAMETER_SET_6
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Group
Indicates that only matching phase 2 authentication sets of the indicated group association are renamed.
Wildcard characters are accepted. 

This parameter specifies the source string for the **DisplayGroup** parameter.
If the **DisplayGroup** parameter value is a localizable string, then this parameter contains an indirect string.
Rule groups organizes rules by influence and allows batch rule modifications.
Using the Set-NetIPsecPhase2AuthSet cmdlet, if the group name is specified for a set of rules, then all of the rules in that group receive the same set of modifications.
It is good practice to specify this parameter with a universal and world-ready indirect @FirewallAPI name. 
Note: The **DisplayGroup** parameter cannot be specified upon object creation using the New-NetIPsecPhase2AuthSet cmdlet, but can be modified using dot notation and the Set-NetIPsecPhase2AuthSet cmdlet.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_5
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the input to this cmdlet.
You can use this parameter, or you can pipe the input to this cmdlet.

```yaml
Type: CimInstance[]
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Indicates that only matching phase 2 authentication sets of the indicated name are renamed.
Wildcard characters are accepted. 

This parameter acts just like a file name, in that only one rule with a given name may exist in a policy store at a time.
During group policy processing and policy merge, rules that have the same name but come from multiple stores being merged, will overwrite one another so that only one exists.
This overwriting behavior is desirable if the rules serve the same purpose.
For instance, all of the firewall rules have specific names, so if an administrator can copy these rules to a GPO, and the rules will override the local versions on a local computer.
Since GPOs can have precedence, if an administrator that gives a rule with a different or more specific rule the same name in a higher-precedence GPO, then it overrides other rules that exist. 

The default value is a randomly assigned value. 

When the defaults for phase 2 encryption are overridden, specify the customized parameters and set this parameter value, making this parameter the new default setting for encryption.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: ID

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NewName
Specifies the new name for one or more phase 2 authentication sets.

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
Targets the policy store from which to retrieve the sets to be renamed. 

A policy store is a container for firewall and IPsec policy. 
The acceptable values for this parameter are:

 -- PersistentStore: Sometimes called static rules, this store contains the persistent policy for the local computer.
This policy is not from GPOs, and has been created manually or programmatically (during application installation) on the computer.
Rules created in this store are attached to the ActiveStore and activated on the computer immediately. 

 -- ActiveStore: This store contains the currently active policy, which is the sum of all policy stores that apply to the computer.
This is the resultant set of policy (RSOP) for the local computer (the sum of all GPOs that apply to the computer), and the local stores (the PersistentStore, the static Windows service hardening (WSH), and the configurable WSH). 

 ---- Group Policy Objects (GPOs) are also policy stores.
Computer GPOs can be specified as follows. 

 ------ `-PolicyStore hostname`. 

 ---- Active Directory GPOs can be specified as follows. 

 ------ `-PolicyStore domain.fqdn.com\GPO_Friendly_Namedomain.fqdn.comGPO_Friendly_Name`. 

 ------ Such as the following. 

 -------- `-PolicyStore localhost`

 -------- `-PolicyStore corp.contoso.com\FirewallPolicy`

 ---- Active Directory GPOs can be created using the New-GPO cmdlet or the Group Policy Management Console. 

 -- RSOP: This read-only store contains the sum of all GPOs applied to the local computer. 

 -- SystemDefaults: This read-only store contains the default state of firewall rules that ship with Windows Server® 2012. 

 -- StaticServiceStore: This read-only store contains all the service restrictions that ship with Windows Server 2012.
Optional and product-dependent features are considered part of Windows Server 2012 for the purposes of WFAS. 

 -- ConfigurableServiceStore: This read-write store contains all the service restrictions that are added for third-party services.
In addition, network isolation rules that are created for Windows Store application containers will appear in this policy store. 

The default value is PersistentStore. 
Note: The Set-NetIPsecPhase2AuthSet cmdlet cannot be used to add an object to a policy store.
An object can only be added to a policy store at creation time with the Copy-NetIPsecPhase2AuthSet cmdlet or with the New-NetIPsecPhase2AuthSet cmdlet.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_4, UNNAMED_PARAMETER_SET_5, UNNAMED_PARAMETER_SET_6
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PolicyStoreSource
Indicates that phase 2 authentication sets that match the indicated policy store source are renamed. 

This parameter contains a path to the policy store where the rule originated if the object is retrieved from the ActiveStore with the TracePolicyStoreSource option set.
This parameter value is automatically generated and should not be modified. 

The monitoring output from this parameter is not completely compatible with the **PolicyStore** parameter.
This parameter value cannot always be passed into the **PolicyStore** parameter.
Domain GPOs are one example in which this parameter contains only the GPO name, not the domain name.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_5
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PolicyStoreSourceType
Indicates that phase 1 authentication sets that match the indicated policy store source type are renamed. 

This parameter describes the type of policy store where the rule originated if the object is retrieved from the ActiveStore with the TracePolicyStoreSource option set.
This parameter value is automatically generated and should not be modified. 
The acceptable values for this parameter are:

 -- Local: The object originates from the local store. 

 -- GroupPolicy: The object originates from a GPO. 

 -- Dynamic: The object originates from the local runtime state.
This policy store name is not valid for use in cmdlets, but may appear when monitoring active policy. 

 -- Generated: The object was generated automatically.
This policy store name is not valid for use in cmdlets, but may appear when monitoring active policy. 

 -- Hardcoded: The object was hard-coded.
This policy store name is not valid for use in cmdlets, but may appear when monitoring active policy.

```yaml
Type: PolicyStoreType[]
Parameter Sets: UNNAMED_PARAMETER_SET_5
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrimaryStatus
Indicates that phase 2 authentication sets that match the indicated primary status are renamed. 

This parameter describes the overall status of the rule. 

 - OK: Indicates that the rule will work as specified. 

 -- Degraded: Indicates that one or more parts of the rule will not be enforced. 

 -- Error: Indicates that the computer is unable to use the rule at all. 

See the Status and StatusCode fields of the object for more detailed status information.

```yaml
Type: PrimaryStatus[]
Parameter Sets: UNNAMED_PARAMETER_SET_5
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Status
Indicates that phase 2 authentication sets that match the indicated status are renamed. 

This parameter describes the status message for the specified status code value.
The status code is a numerical value that indicates any syntax, parsing, or runtime errors in the rule.
This parameter value should not be modified.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_5
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
Indicates that the phase 2 authentication sets that match the indicated policy store are renamed. 

This parameter specifies that the name of the source GPO is queried and set to the **PolicyStoreSource** parameter value.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_4, UNNAMED_PARAMETER_SET_5, UNNAMED_PARAMETER_SET_6
Aliases: 

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
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_NetConSecRule[]
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_NetIKEP2AuthSet[]
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Copy-NetIPsecPhase2AuthSet](./Copy-NetIPsecPhase2AuthSet.md)

[Get-NetIPsecRule](./Get-NetIPsecRule.md)

[New-NetIPsecMainModeRule](./New-NetIPsecMainModeRule.md)

[New-NetIPsecPhase2AuthSet](./New-NetIPsecPhase2AuthSet.md)

[Open-NetGPO](./Open-NetGPO.md)

[Remove-NetIPsecQuickModeCryptoSet](./Remove-NetIPsecQuickModeCryptoSet.md)

[Save-NetGPO](./Save-NetGPO.md)

[Set-NetIPsecPhase2AuthSet](./Set-NetIPsecPhase2AuthSet.md)

[New-GPO](../grouppolicy/New-GPO.md)

