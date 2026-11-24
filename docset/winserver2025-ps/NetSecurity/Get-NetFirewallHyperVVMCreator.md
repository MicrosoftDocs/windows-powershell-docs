---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: NetFirewallHyperVVMCreator.cmdletDefinition.cdxml-help.xml
Module Name: NetSecurity
ms.date: 8/25/2023
online version: https://docs.microsoft.com/powershell/module/netsecurity/get-netfirewallhypervvmcreator?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NetFirewallHyperVVMCreator
---

# Get-NetFirewallHyperVVMCreator

## SYNOPSIS
Retrieves Hyper-V firewall VM Creators from the target computer.

## SYNTAX

### GetAll (Default)
```
Get-NetFirewallHyperVVMCreator [-All] [-CimSession <CimSession[]>] [-ThrottleLimit <int>] [-AsJob]  [<CommonParameters>]
```

## DESCRIPTION

The **Get-NetFirewallHyperVVMCreator** cmdlet returns the instances of the Hyper-V firewall VM creators on the system.


A Hyper-V firewall rule can be scoped to apply only to Hyper-V firewall ports created by specific Hyper-V VM creators. This cmdlet is used to query the list of creators currently on the system.

A rule can be scoped to a specific VM creator even if it is not yet on the system. This can be useful when configuring policy when a particular application may be installed at an unknown point in time.


## EXAMPLES

### EXAMPLE 1
```
PS C:\> Get-NetFirewallHyperVVMCreator
```

This example retrieves all the Hyper-V firewall VM creators that are currently on the system.


## PARAMETERS

### -All
Specifies that all Hyper-V firewall VM creators should be retrieved.

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

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\NetFirewallHyperVVMCreator
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Get-NetfirewallHyperVRule](./Get-NetFirewallHyperVRule.md)

[Get-NetFirewallHyperVPort](./Get-NetFirewallHyperVPort.md)

[Get-NetFirewallHyperVVMSetting](./Get-NetFirewallHyperVVMSetting.md)

[Set-NetFirewallHyperVVMSetting](./Set-NetFirewallHyperVVMSetting.md)