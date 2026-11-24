---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: NetFirewallHyperVRule.cmdletDefinition.cdxml-help.xml
Module Name: NetSecurity
ms.date: 8/25/2023
online version: https://docs.microsoft.com/powershell/module/netsecurity/rename-netfirewallhypervrule?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Rename-NetFirewallHyperVRule
---

# Rename-NetFirewallHyperVRule

## SYNOPSIS
Renames a single Hyper-V firewall rule.

## SYNTAX

### GetAll (Default)
```
Rename-NetFirewallHyperVRule -NewName <string> [-All] [-PolicyStore <string>] [-CimSession <CimSession[]>] [-ThrottleLimit <int>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByName
```
Rename-NetFirewallHyperVRule [-Name] <string[]> -NewName <string> [-PolicyStore <string>] [-CimSession <CimSession[]>] [-ThrottleLimit <int>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByDisplayName
```
Rename-NetFirewallHyperVRule -DisplayName <string[]> -NewName <string> [-PolicyStore <string>] [-CimSession <CimSession[]>] [-ThrottleLimit <int>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByQuery
```
Rename-NetFirewallHyperVRule -NewName <string> [-Direction {Inbound | Outbound}] [-VMCreatorId <string[]>] [-Protocol <string[]>] [-Action {NotConfigured | Allow | Block}] [-Enabled {True | False}] [-EnforcementStatus {Unknown | OK | PartiallyEnforced | NoApplicablePorts | ParsingError | Error}] [-PolicyStoreSourceType {None | Local | MDM}] [-PolicyStore <string>] [-CimSession <CimSession[]>] [-ThrottleLimit <int>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm]  [<CommonParameters>]
```

### InputObject (cdxml)
```
Rename-NetFirewallHyperVRule -InputObject <CimInstance#MSFT_NetFirewallHyperVRule[]> -NewName <string> [-CimSession <CimSession[]>] [-ThrottleLimit <int>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm]  [<CommonParameters>]
```

## DESCRIPTION

The **Rename-NetFirewallHyperVRule** cmdlet renames an existing Hyper-V firewall rule. When creating a rule, if the Name parameter is not specified, then a random GUID is used. This cmdlet specifies a friendly and descriptive rule name. The newly specified name, using the NewName parameter, must still be unique since it identifies a single rule object on the computer.

This cmdlet renames the Hyper-V firewall rule with the Name parameter, DisplayName parameter, or rule properties. Only one Hyper-V firewall rule can be renamed at a time.


To modify the DisplayName parameter, run the Set-NetFirewallHyperVRule cmdlet with the NewDisplayName parameter.

The names are unique identifiers for rules, similar to file names. Each name must be unique within a given policy store.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Rename-NetFirewallHyperVRule -Name "{ed8384a9-a78b-4d0d-8f3d-eb5615edb4a0}" -NewName "Contoso-Out-TCP-Block"
```

This example renames a Hyper-V firewall rule so that the identifier is descriptive and user friendly.

## PARAMETERS

### -Action
Specifies that matching Hyper-V firewall rules of the indicated action are renamed.
The acceptable values for this parameter are: Allow or Block.

- Allow: Network packets that match all criteria specified in this rule are permitted through the firewall.
This is the default value.
- Block: Network packets that match all criteria specified in this rule are dropped by the firewall.

```yaml
Type: Action
Parameter Sets: (All)
Aliases:
Accepted values: NotConfigured, Allow, Block
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

### -Direction
Specifies that matching Hyper-V firewall rules of the indicated direction are renamed.
This parameter specifies which direction of traffic to match with this rule.
The acceptable values for this parameter are: Inbound or Outbound.

```yaml
Type: Direction
Parameter Sets: (All)
Aliases:
Accepted values: Inbound, Outbound
Required: False
Position: Named
Default value: Inbound
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisplayName
Specifies that only matching Hyper-V firewall rules of the indicated display name are renamed. Wildcard characters are accepted.

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

### -Enabled
Specifies that matching Hyper-V firewall rules of the indicated state are renamed.
This parameter specifies that the rule object is administratively enabled or administratively disabled.
The acceptable values for this parameter are:
- True: Specifies the rule is currently enabled.
- False: Specifies the rule is currently disabled.

Note that the type of this parameter is not Boolean, therefore `$true` and `$false` variables are not acceptable values here. Use "True" and "False" text strings instead.


A disabled rule will not actively modify computer behavior, but the management construct still exists on the computer so it can be re-enabled.

```yaml
Type: Enabled
Parameter Sets: (All)
Aliases:
Accepted values: True, False
Required: False
Position: Named
Default value: True
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnforcementStatus
Specifies that firewall rules that match the indicated enforcement status are renamed.
This parameter specifies the overall status of the rule.
- OK: Specifies that the rule will work as specified.
- PartiallyEnforced: Specifies that one or more parts of the rule will not be enforced.
- NoApplicablePorts: Specifies that the rule is functioning as expected, but there are no ports applicable for this rule and therefore is not active.
- ParsingError: Specifies that the rule is corrupted and the computer is unable to use the rule at all.
- Error: Specifies that the computer is unable to use the rule at all.

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


### -Name
Specifies that only matching Hyper-V firewall rules of the indicated name are renamed.
This name serves as the unique identifier for this rule. This parameter acts just like a file name, in that only one rule with a given name may exist in a policy store at a time.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ID
Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```


### -NewName
Specifies the new name for the Hyper-V firewall rule.

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

### -PolicyStore
Targets the policy store from which to rename the rules.
A policy store is a container for firewall policy.
The acceptable values for this parameter are:
- PersistentStore: Sometimes called static rules, this store contains the persistent policy for the local computer.
This policy is not from GPOs, and has been created manually or programmatically (during application installation) on the computer.
Rules created in this store are attached to the ActiveStore and activated on the computer immediately.
- ActiveStore: This store contains the currently active policy, which is the sum of all policy stores that apply to the computer.
- SystemDefaults: This read-only store contains the default state of firewall rules.
- MDM: This store contains the rules configured via MDM.

By default, the PersistentStore is queried.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PolicyStoreSourceType
Specifies that Hyper-V firewall rules that match the indicated policy store source type are renamed.
This parameter value is automatically generated and should not be modified.
The acceptable values for this parameter are:
- Local: The object originates from the local store.
- MDM: The object originates from the MDM store.

By default, the Local store is queried.

```yaml
Type: PolicyStoreType[]
Parameter Sets: ByQuery
Aliases:
Accepted values: None, Local, MDM

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Protocol
Specifies that only matching Hyper-V firewall rules with the indicated protocol are renamed.

The acceptable values for this parameter are:
- Protocols by number:  0-255.
- Protocols by name:  TCP, UDP, ICMPv4, or ICMPv6.

```yaml
Type: String
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
If this parameter is omitted or a value of `0` is entered, Windows PowerShell calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.

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

### -VMCreatorId
Specifies that only matching Hyper-V firewall rules with the specified VMCreatorId are renamed.
The format for this value is a GUID enclosed in brackets, such as '{9E288F02-CE00-4D9E-BE2B-14CE463B0298}'.


```yaml
Type: String
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

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\NetFirewallHyperVRule
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[New-NetFirewallHyperVRule](./New-NetFirewallHyperVRule.md)

[Get-NetFirewallHyperVRule](./Get-NetFirewallHyperVRule.md)

[Enable-NetFirewallHyperVRule](./Enable-NetFirewallHyperVRule.md)

[Disable-NetFirewallHyperVRule](./Disable-NetFirewallHyperVRule.md)

[Remove-NetFirewallHyperVRule](./Remove-NetFirewallHyperVRule.md)

[Set-NetFirewallHyperVRule](./Set-NetFirewallHyperVRule.md)

[Get-NetfirewallHyperVVMCreator](./Get-NetFirewallHyperVVMCreator.md)