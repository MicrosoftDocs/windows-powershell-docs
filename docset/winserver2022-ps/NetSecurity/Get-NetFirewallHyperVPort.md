---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: NetFirewallHyperVPort.cmdletDefinition.cdxml-help.xml
Module Name: NetSecurity
ms.date: 8/25/2023
online version: https://docs.microsoft.com/powershell/module/netsecurity/get-netfirewallhypervport?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NetFirewallHyperVPort
---

# Get-NetFirewallHyperVPort

## SYNOPSIS
Retrieves Hyper-V firewall ports from the target computer.

## SYNTAX

### GetAll (Default)
```
Get-NetFirewallHyperVPort [-All] [-CimSession <CimSession[]>] [-ThrottleLimit <int>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION

The **Get-NetFirewallHyperVPort** cmdlet returns the instances of the Hyper-V firewall ports. Hyper-V firewall rules are applied on a per-port basis. This cmdlet queries the active ports on the system and displays associated data about the port.


## EXAMPLES

### EXAMPLE 1
```
PS C:\> Get-NetFirewallHyperVPort
```

This example retrieves all the Hyper-V firewall ports that are currently on the system.


## PARAMETERS

### -All
Specifies that all Hyper-V firewall ports should be retrieved.

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

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\NetFirewallHyperVPort
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Get-NetfirewallHyperVRule](./Get-NetFirewallHyperVRule.md)

[Get-NetfirewallHyperVVMCreator](./Get-NetFirewallHyperVVMCreator.md)

[Get-NetFirewallHyperVVMSetting](./Get-NetFirewallHyperVVMSetting.md)

[Set-NetFirewallHyperVVMSetting](./Set-NetFirewallHyperVVMSetting.md)