---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: NetFirewallHyperVVMSetting.cmdletDefinition.cdxml-help.xml
Module Name: NetSecurity
ms.date: 8/25/2023
online version: https://docs.microsoft.com/powershell/module/netsecurity/set-netfirewallhypervvmsetting?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-NetFirewallHyperVVMSetting
---

# Set-NetFirewallHyperVVMSetting

## SYNOPSIS
Configures Hyper-V firewall per-VM settings on the target computer.

## SYNTAX

### ByName
```
Set-NetFirewallHyperVVMSetting [-Name] <string[]> [-Enabled {False | True | NotConfigured}] [-DefaultInboundAction {NotConfigured | Allow | Block}] [-DefaultOutboundAction {NotConfigured | Allow | Block}] [-LoopbackEnabled {False | True | NotConfigured}] [-CimSession <CimSession[]>] [-ThrottleLimit <int>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm]  [<CommonParameters>]
```

### InputObject (cdxml)
```
Set-NetFirewallHyperVVMSetting -InputObject <CimInstance#MSFT_NetFirewallHyperVVMSetting[]> [-Enabled {False | True | NotConfigured}] [-DefaultInboundAction {NotConfigured | Allow | Block}] [-DefaultOutboundAction {NotConfigured | Allow | Block}] [-LoopbackEnabled {False | True | NotConfigured}] [-CimSession <CimSession[]>] [-ThrottleLimit <int>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm]  [<CommonParameters>]
```

## DESCRIPTION

The **Set-NetFirewallHyperVVMSetting** cmdlet configures settings for the Hyper-V firewall per-VM settings on the system. These settings are applicable to all Hyper-V firewall ports created by a specific Hyper-V firewall VM creator.


This cmdlet should be used when a Hyper-V VM creator has registered its VM creator ID with the system, when another Hyper-V setting is already configured for the specified VM creator ID, or when a Hyper-V firewall port is created with the specified VM creator ID. If none of the above are true, then the New-NetFirewallHyperVVMSetting cmdlet should be used.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Set-NetFirewallHyperVVMSetting -Name '9E288F02-CE00-4D9E-BE2B-14CE463B0298}' -LoopbackEnabled True
```

This example updates the LoopbackEnabled setting for all Hyper-V firewall ports created by the Hyper-V firewall VM creator specified.


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

### -DefaultInboundAction
Specifies how to filter inbound traffic that does not match any Hyper-V firewall rules.


This setting applies the configuration to all profiles. For configuring at a per-profile granularity, use the `Set-NetFirewallHyperVProfile` cmdlet.

The acceptable values for this parameter are: NotConfigured, Allow, or Block. 

- Block: Blocks inbound network traffic that does not match an inbound rule. 
- Allow: Allows all inbound network traffic, whether or not it matches an inbound rule. 
- NotConfigured: Resets this value back to its default.

The default setting is Block.

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

### -DefaultOutboundAction
Specifies how to filter outbound traffic that does not match any Hyper-V firewall rules.


This setting applies the configuration to all profiles. For configuring at a per-profile granularity, use the `Set-NetFirewallHyperVProfile` cmdlet.

The acceptable values for this parameter are: NotConfigured, Allow, or Block. 

- Block: Blocks outbound network traffic that does not match an outbound rule. 
- Allow: Allows all outbound network traffic, whether or not it matches an outbound rule. 
- NotConfigured: Resets this value back to its default.

The default setting is Block.

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

### -Enabled
Determines whether or not the Hyper-V firewall is active and enforced.

This setting applies the configuration to all profiles. For configuring at a per-profile granularity, use the `Set-NetFirewallHyperVProfile` cmdlet.

The acceptable values for this parameter are: False, True, or NotConfigured.

- True: Enables Windows Hyper-V firewall.
- False: Disables Windows Hyper-V firewall.
- NotConfigured: Resets this value back to its default.

The default setting is True.

```yaml
Type: GpoBoolean
Parameter Sets: (All)
Aliases: 
Accepted values: False, True, NotConfigured

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LoopbackEnabled
Determines whether or not guest-host loopback traffic is allowed.

This setting is orthogonal to any existing Hyper-V firewall rules. That is, both this setting and the set of Hyper-V firewall rules must both be configured to allow guest-host communication. Furthermore, if either this setting or a Hyper-V firewall rule blocks the communication, it will be blocked.

The acceptable values for this parameter are: False, True, or NotConfigured. 

- True: Hyper-V firewall allows traffic between guest and host.
- False: Hyper-V firewall blocks traffic between guest and host.
- NotConfigured: Resets this value back to its default.

The default setting is False.

```yaml
Type: GpoBoolean
Parameter Sets: (All)
Aliases: 
Accepted values: False, True, NotConfigured

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllowHostPolicyMerge
Specifies that the host firewall policy should be merged into the effective policy. 

This setting controls whether host firewall profile settings (DefaultInboundAction, DefaultOutboundAction, Enabled, and AllowLocalFirewallRules) as well as host firewall rules (only rules that are IP 5-tuple based, that is, not having any local conditions such as application) should be applicable to Hyper-V firewall.


Policy configurations may come from many stores. If this setting is True, the following order of precedence is used for determining the effective policy (highest priority to lowest priority):
- Host Firewall Group Policy
- Hyper-V Firewall MDM
- Host Firewall MDM
- Hyper-V Firewall Local
- Host Firewall Local

The acceptable values for this parameter are: False, True, or NotConfigured.

- True: Host firewall rules and settings are applied to Hyper-V firewall.

- False: Host firewall rules and settings are not applied to Hyper-V firewall
- NotConfigured: Resets this value back to its default.

The default setting is True.

```yaml
Type: GpoBoolean
Parameter Sets: (All)
Aliases: 
Accepted values: False, True, NotConfigured

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies that the settings are applicable only to the Hyper-V firewall VM creator with the matching Id.
The format for this value is a GUID enclosed in brackets: '{9E288F02-CE00-4D9E-BE2B-14CE463B0298}'.

```yaml
Type: String
Parameter Sets: (All)
Aliases: VMCreatorId
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\NetFirewallHyperVVMSettings
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Get-NetfirewallHyperVRule](./Get-NetFirewallHyperVRule.md)

[Get-NetfirewallHyperVPort](./Get-NetFirewallHyperVPort.md)

[Get-NetfirewallHyperVVMCreator](./Get-NetFirewallHyperVVMCreator.md)

[Get-NetFirewallHyperVVMSetting](./Get-NetFirewallHyperVVMSetting.md)

[New-NetFirewallHyperVVMSetting](./New-NetFirewallHyperVVMSetting.md)

[Get-NetFirewallHyperVProfile](./Get-NetFirewallHyperVProfile.md)

[New-NetFirewallHyperVProfile](./New-NetFirewallHyperVProfile.md)

[Set-NetFirewallHyperVProfile](./Set-NetFirewallHyperVProfile.md)