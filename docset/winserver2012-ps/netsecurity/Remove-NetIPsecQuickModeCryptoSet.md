---
external help file: NetSecurity_Function.xml
Module Name: NetSecurity
online version: https://learn.microsoft.com/powershell/module/netsecurity/remove-netipsecquickmodecryptoset?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Remove-NetIPsecQuickModeCryptoSet

## SYNOPSIS
Deletes all of the quick mode cryptographic sets that match the specified criteria.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Remove-NetIPsecQuickModeCryptoSet [-All] [-AsJob] [-CimSession <CimSession[]>] [-GPOSession <String>]
 [-PassThru] [-PolicyStore <String>] [-ThrottleLimit <Int32>] [-TracePolicyStore] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Remove-NetIPsecQuickModeCryptoSet [-AsJob] [-CimSession <CimSession[]>] [-GPOSession <String>] [-PassThru]
 [-PolicyStore <String>] [-ThrottleLimit <Int32>] [-TracePolicyStore] -DisplayName <String[]> [-Confirm]
 [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Remove-NetIPsecQuickModeCryptoSet [-Name] <String[]> [-AsJob] [-CimSession <CimSession[]>]
 [-GPOSession <String>] [-PassThru] [-PolicyStore <String>] [-ThrottleLimit <Int32>] [-TracePolicyStore]
 [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_4
```
Remove-NetIPsecQuickModeCryptoSet [-AsJob] [-CimSession <CimSession[]>] [-GPOSession <String>] [-PassThru]
 [-PolicyStore <String>] [-ThrottleLimit <Int32>] [-TracePolicyStore] -AssociatedNetIPsecRule <CimInstance>
 [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_5
```
Remove-NetIPsecQuickModeCryptoSet [-AsJob] [-CimSession <CimSession[]>] [-PassThru] [-ThrottleLimit <Int32>]
 -InputObject <CimInstance[]> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_6
```
Remove-NetIPsecQuickModeCryptoSet [-AsJob] [-CimSession <CimSession[]>] [-Description <String[]>]
 [-DisplayGroup <String[]>] [-GPOSession <String>] [-Group <String[]>] [-PassThru]
 [-PerfectForwardSecrecyGroup <DiffieHellmanGroup[]>] [-PolicyStore <String>] [-PolicyStoreSource <String[]>]
 [-PolicyStoreSourceType <PolicyStoreType[]>] [-PrimaryStatus <PrimaryStatus[]>] [-Status <String[]>]
 [-ThrottleLimit <Int32>] [-TracePolicyStore] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Remove-NetIPsecQuickModeCryptoSet** cmdlet permanently deletes one or more quick mode cryptographic sets from the specified policy store.

The cmdlet gets one or more quick mode cryptographic sets to be deleted with the **Name** parameter (default), The **DisplayName** parameter, the **Group** parameter, or by associated IPsec rule.
The resulting queried set is removed from the computer.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Remove-NetIPsecQuickModeCryptoSet
```

This example removes all of the static local main mode cryptographic sets.
This cmdlet is useful for removing any policy that conflicts with the domain GPO.

### EXAMPLE 2
```
PS C:\>Remove-NetIPsecQuickModeCryptoSet -DisplayName "DirectAccess - Phase2 Crypto Set"
```

This example deletes a set based on the localized name.

### EXAMPLE 3
```
PS C:\>$ipsRule = Get-NetIPsecRule -DisplayName "Transport Mode - CorpNet IPv4 - AuthIP"



PS C:\>Remove-NetIPsecQuickModeCryptoSet -InputObject $ipsRule
```

This example removes all of the quick mode cryptographic sets that are associated with an IPsec rule.

## PARAMETERS

### -All
Indicates that all of the quick mode cryptographic sets within the specified policy store are removed.

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
Gets the quick mode cryptographic sets that are associated, via the pipeline, with the input IPsec rule to be removed. 

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
Specifies that matching quick mode cryptographic sets of the indicated description are removed.
Wildcard characters are accepted. 

This parameter provides information about the quick mode cryptographic sets.
This parameter specifies a localized, user-facing description of the object.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_6
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisplayGroup
Specifies that only matching quick mode cryptographic sets of the indicated group association are removed.
Wildcard characters are accepted. 

The **Group** parameter specifies the source string for this parameter.
If the value for this parameter is a localizable string, then the **Group** parameter contains an indirect string.
Rule groups can be used to organize rules by influence and allows batch rule modifications.
Using the Set-NetIPsecQuickModeCryptoSet cmdlet, if the group name is specified for a set of rules, then all of the rules in that group receive the same set of modifications.
It is a good practice to specify the **Group** parameter with a universal and world-ready indirect @FirewallAPI name. 
Note: This parameter cannot be specified upon object creation using the New-NetIPsecQuickModeCryptoSet cmdlet, but can be modified using dot notation and the Set-NetIPsecQuickModeCryptoSet cmdlet.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_6
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisplayName
Specifies that only matching quick mode cryptographic sets of the indicated display name are removed.
Wildcard characters are accepted. 

This parameter specifies the localized, user-facing name of the quick mode cryptographic set being created.
When creating a set this parameter is required.
This parameter value is locale-dependent.
If the object is not modified, this parameter value may change in certain circumstances.
When writing scripts in multi-lingual environments, the **Name** parameter should be used instead, where the default value is a randomly assigned value. 
Note: This parameter value cannot be All.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GPOSession
Specifies the network GPO from which to retrieve the sets to be removed. 

This parameter is used in the same way as the **PolicyStore** parameter.
When modifying Group Policy objects (GPOs) in Windows PowerShell®, each change to a GPO requires the entire GPO to be loaded, modified, and saved back.
On a busy Domain Controller (DC), this can be a slow and resource-heavy operation.
A GPO Session loads a domain GPO onto the local computer and makes all changes in a batch, before saving it back.
This reduces the load on the DC and speeds up the Windows PowerShell cmdlets.
To load a GPO Session, use the Open-NetGPO cmdlet.
To save a GPO Session, use the Save-NetGPO cmdlet.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_3, UNNAMED_PARAMETER_SET_4, UNNAMED_PARAMETER_SET_6
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Group
Specifies that only matching quick mode cryptographic sets of the indicated group association are removed.
Wildcard characters are accepted. 

This parameter specifies the source string for the **DisplayGroup** parameter.
If the **DisplayGroup** parameter value is a localizable string, then this parameter contains an indirect string.
Rule groups organizes rules by influence and allows batch rule modifications.
Using the Set-NetIPsecQuickModeCryptoSet cmdlet, if the group name is specified for a set of rules, then all of the rules in that group receive the same set of modifications.
It is good practice to specify this parameter with a universal and world-ready indirect @FirewallAPI name. 
Note: The **DisplayGroup** parameter cannot be specified upon object creation using the New-NetIPsecQuickModeCryptoSet cmdlet, but can be modified using dot notation and the Set-NetIPsecQuickModeCryptoSet cmdlet.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_6
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
Parameter Sets: UNNAMED_PARAMETER_SET_5
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies that only matching quick mode cryptographic sets of the indicated name are removed.
Wildcard characters are accepted. 

This parameter acts just like a filename, in that only one rule with a given name may exist in a policy store at a time.
During group policy processing and policy merge, rules that have the same name but come from multiple stores being merged, will overwrite one another so that only one exists.
This overwriting behavior is desirable if the rules serve the same purpose.
For instance, all of the firewall rules have specific names, so if an administrator can copy these rules to a GPO, and the rules will override the local versions on a local computer.
Since GPOs can have precedence, if an administrator that gives a rule with a different or more specific rule the same name in a higher-precedence GPO, then it overrides other rules that exist. 

The default value is a randomly assigned value. 

When the defaults for quick mode encryption are overridden, specify the customized parameters and set this parameter value, making this parameter the new default setting for encryption.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: ID

Required: True
Position: 1
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

### -PerfectForwardSecrecyGroup
Specifies that matching main mode cryptographic sets of the indicated Diffie-Hellman group are removed. 

This parameter specifies the Diffie-Hellman group to use for session key perfect forward secrecy. 
The acceptable values for this parameter are: None, DH1, DH2, DH14, DH19, DH20, DH24, or SameAsMainMode. 

The default value is None.

```yaml
Type: DiffieHellmanGroup[]
Parameter Sets: UNNAMED_PARAMETER_SET_6
Aliases: PfsGroup

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PolicyStore
Specifies the policy store from which to retrieve the sets to be removed. 

A policy store is a container for firewall and IPsec policy. 
The acceptable values for this parameter are:

 -- PersistentStore: Sometimes called static rules, this store contains the persistent policy for the local computer.
This policy is not from GPOs, and has been created manually or programmatically (during application installation) on the computer.
Rules created in this store are attached to the ActiveStore and activated on the computer immediately.
This is the default value. 

 -- ActiveStore: This store contains the currently active policy, which is the sum of all policy stores that apply to the computer.
This is the resultant set of policy (RSOP) for the local computer (the sum of all GPOs that apply to the computer), and the local stores (the PersistentStore, the static Windows service hardening (WSH), and the configurable WSH). 

 ---- GPOs are also policy stores.
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
Note: The Set-NetIPsecQuickModeCryptoSet cmdlet cannot be used to add an object to a policy store.
An object can only be added to a policy store at creation time with the New-NetIPsecQuickModeCryptoSet cmdlet or with this cmdlet.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_3, UNNAMED_PARAMETER_SET_4, UNNAMED_PARAMETER_SET_6
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PolicyStoreSource
Specifies that quick mode cryptographic sets that match the indicated policy store source are removed. 

This parameter contains a path to the policy store where the rule originated if the object is retrieved from the ActiveStore with the TracePolicyStoreSource option set.
This parameter value is automatically generated and should not be modified. 

The monitoring output from this parameter is not completely compatible with the **PolicyStore** parameter.
This parameter value cannot always be passed into the **PolicyStore** parameter.
Domain GPOs are one example in which this parameter contains only the GPO name, not the domain name.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_6
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PolicyStoreSourceType
Specifies that quick mode cryptographic sets that match the indicated policy store source type are removed. 

This parameter describes the type of policy store where the rule originated if the object is retrieved from the ActiveStore with the TracePolicyStoreSource option set.
This parameter value is automatically generated and should not be modified. 
The acceptable values for this parameter are:

 -- Local: The object originates from the local store. 

 -- GroupPolicy: The object originates from a GPO. 

 -- Dynamic: The object originates from the local runtime state.
This policy store name is not valid for use in the cmdlets, but may appear when monitoring active policy. 

 -- Generated: The object was generated automatically.
This policy store name is not valid for use in the cmdlets, but may appear when monitoring active policy. 

 -- Hardcoded: The object was hard-coded.
This policy store name is not valid for use in the cmdlets, but may appear when monitoring active policy.

```yaml
Type: PolicyStoreType[]
Parameter Sets: UNNAMED_PARAMETER_SET_6
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrimaryStatus
Specifies that quick mode cryptographic sets that match the indicated primary status are removed. 

This parameter describes the overall status of the rule. 

 -- OK: Specifies that the rule will work as specified. 

 -- Degraded: Specifies that one or more parts of the rule will not be enforced. 

 -- Error: Specifies that the computer is unable to use the rule at all. 

See the Status and StatusCode fields of the object for more detailed status information.

```yaml
Type: PrimaryStatus[]
Parameter Sets: UNNAMED_PARAMETER_SET_6
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Status
Specifies that quick mode cryptographic sets that match the indicated status are retrieved. 

This parameter describes the status message for the specified status code value.
The status code is a numerical value that indicates any syntax, parsing, or runtime errors in the rule.
This parameter value should not be modified.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_6
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
Indicates that the quick mode cryptographic sets that match the indicated policy store are removed. 

This parameter specifies that the name of the source GPO is queried and set to the **PolicyStoreSource** parameter value.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_3, UNNAMED_PARAMETER_SET_4, UNNAMED_PARAMETER_SET_6
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

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_NetIKEQMCryptoSet[]
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Get-NetIPsecRule](./Get-NetIPsecRule.md)

[New-NetIPsecMainModeRule](./New-NetIPsecMainModeRule.md)

[New-NetIPsecQuickModeCryptoSet](./New-NetIPsecQuickModeCryptoSet.md)

[Open-NetGPO](./Open-NetGPO.md)

[Save-NetGPO](./Save-NetGPO.md)

[Set-NetIPsecQuickModeCryptoSet](./Set-NetIPsecQuickModeCryptoSet.md)

[New-GPO](../grouppolicy/New-GPO.md)

