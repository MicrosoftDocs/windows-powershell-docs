---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: NetFirewallHyperVVMSetting.cmdletDefinition.cdxml-help.xml
Module Name: NetSecurity
ms.date: 8/25/2023
online version: https://docs.microsoft.com/powershell/module/netsecurity/get-netfirewallhypervvmsetting?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NetFirewallHyperVVMSetting
---

# Get-NetFirewallHyperVVMSetting

## SYNOPSIS
Retrieves Hyper-V firewall per-VM settings from the target computer.

## SYNTAX

### GetAll (Default)
```
Get-NetFirewallHyperVVMSetting [-All] [-PolicyStore <string>] [-CimSession <CimSession[]>] [-ThrottleLimit <int>] [-AsJob]  [<CommonParameters>]
```

### ByName
```
Get-NetFirewallHyperVVMSetting [-Name] <string[]> [-PolicyStore <string>] [-CimSession <CimSession[]>] [-ThrottleLimit <int>] [-AsJob]  [<CommonParameters>]
```

## DESCRIPTION

The **Get-NetFirewallHyperVVMSetting** cmdlet returns the Hyper-V firewall per-VM settings on the system. These settings are applicable to all Hyper-V firewall ports created by a specific Hyper-V firewall VM creator.


These settings are configurable on a per-store basis. By default, this cmdlet queries the local store.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Get-NetFirewallHyperVVMSetting
```

This example retrieves all of the Hyper-V firewall per-VM settings. With no parameters, this cmdlet queries the settings in the local store.


### EXAMPLE 2
```
PS C:\> Get-NetFirewallHyperVVMSetting -Name '{9E288F02-CE00-4D9E-BE2B-14CE463B0298}'
```

This example retrieves all the Hyper-V firewall per-VM settings for the specified VM creator ID.


### EXAMPLE 3
```
PS C:\> Get-NetFirewallHyperVVMSetting -PolicyStore ActiveStore
```

This example retrieves all the Hyper-V firewall per-VM settings from the ActiveStore.


## PARAMETERS

### -All
Specifies that all Hyper-V firewall per-VM settings should be retrieved.

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

### -Name
Specifies that only matching Hyper-V firewall per-VM settings of the indicated Hyper-V firewall VM creator should be retrieved.
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

### -PolicyStore
Targets the policy store from which to retrieve the rules. 
A policy store is a container for firewall policy. 
The acceptable values for this parameter are:
- PersistentStore: Sometimes called static rules, this store contains the persistent policy for the local computer.
This policy is not from GPOs, and has been created manually or programmatically (during application installation) on the computer.
Rules created in this store are attached to the ActiveStore and activated on the computer immediately. 
- ActiveStore: This store contains the currently active policy, which is the sum of all policy stores that apply to the computer.
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

[New-NetFirewallHyperVVMSetting](./New-NetFirewallHyperVVMSetting.md)

[Set-NetFirewallHyperVVMSetting](./Set-NetFirewallHyperVVMSetting.md)

[Get-NetFirewallHyperVProfile](./Get-NetFirewallHyperVProfile.md)

[New-NetFirewallHyperVProfile](./New-NetFirewallHyperVProfile.md)

[Set-NetFirewallHyperVProfile](./Set-NetFirewallHyperVProfile.md)