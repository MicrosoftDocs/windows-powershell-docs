---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: NetFirewallHyperVProfile.cmdletDefinition.cdxml-help.xml
Module Name: NetSecurity
ms.date: 8/25/2023
online version: https://docs.microsoft.com/powershell/module/netsecurity/set-netfirewallhypervprofile?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-NetFirewallHyperVProfile
---

# Set-NetFirewallHyperVProfile

## SYNOPSIS
Configures Hyper-V firewall profile settings on the target computer.

## SYNTAX

### Query (cdxml) (Default)
```
Set-NetFirewallHyperVProfile [-PolicyStore <string>] [-GPOSession <string>] [-Name <string>] [-Profile {Any | Domain | Private | Public | NotApplicable}] [-CimSession <CimSession[]>] [-ThrottleLimit <int>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

The **Set-NetFirewallHyperVProfile** cmdlet configures the Hyper-V firewall profile settings on the system. These settings are applicable to all Hyper-V firewall ports created by a specific Hyper-V firewall VM creator. These settings apply to the VM only when the profile is active.

This cmdlet should be used when a Hyper-V VM creator has registered its VM creator ID with the system, when another Hyper-V setting is already configured for the specified VM creator ID, or when a Hyper-V firewall port is created with the specified VM creator ID. If none of the above are true, then the New-NetFirewallHyperVProfile cmdlet should be used.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Set-NetFirewallHyperVProfile -Name '{9E288F02-CE00-4D9E-BE2B-14CE463B0298}' -Profile Public -Enabled True
```

This example configures the Enabled setting on the Public profile for all Hyper-V firewall ports created by the Hyper-V firewall VM creator specified.

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

### -AllowLocalFirewallRules
Specifies that the local firewall rules should be merged into the effective policy.
The acceptable values for this parameter are: False, True, or NotConfigured. 

- True: The firewall rules defined by the local administrator are merged with firewall rules from MDM and are applied to the computer. 
- False: The firewall rules defined by the local administrator are ignored, and only firewall rules from MDM are applied to the computer. 
- NotConfigured: This resets the value back to the default.

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
Specifies that the settings are applicable only to the Hyper-V firewall VM creator with the matching ID.
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

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\NetFirewallHyperVProfile
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Get-NetfirewallHyperVRule](./Get-NetFirewallHyperVRule.md)

[Get-NetfirewallHyperVPort](./Get-NetFirewallHyperVPort.md)

[Get-NetfirewallHyperVVMCreator](./Get-NetFirewallHyperVVMCreator.md)

[Get-NetFirewallHyperVVMSetting](./Get-NetFirewallHyperVVMSetting.md)

[Set-NetFirewallHyperVVMSetting](./Set-NetFirewallHyperVVMSetting.md)

[Get-NetFirewallHyperVProfile](./Get-NetFirewallHyperVProfile.md)

[New-NetFirewallHyperVProfile](./New-NetFirewallHyperVProfile.md)

[Set-NetFirewallHyperVProfile](./Set-NetFirewallHyperVProfile.md)