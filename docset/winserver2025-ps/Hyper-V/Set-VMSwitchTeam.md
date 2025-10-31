---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hyper-v/set-vmswitchteam?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-VMSwitchTeam
---

# Set-VMSwitchTeam

## SYNOPSIS
Configures a virtual switch team.

## SYNTAX

### SwitchName_NetAdapterName (Default)
```
Set-VMSwitchTeam [-ComputerName <String[]>] [-Name] <String[]> [-NetAdapterName <String[]>]
 [-TeamingMode <VMSwitchTeamingMode>] [-LoadBalancingAlgorithm <VMSwitchLoadBalancingAlgorithm>] [-Passthru]
 [-CimSession <CimSession[]>] [-Credential <PSCredential[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SwitchName_NetAdapterInterfaceDescription
```
Set-VMSwitchTeam [-ComputerName <String[]>] [-Name] <String[]> [-NetAdapterInterfaceDescription <String[]>]
 [-TeamingMode <VMSwitchTeamingMode>] [-LoadBalancingAlgorithm <VMSwitchLoadBalancingAlgorithm>] [-Passthru]
 [-CimSession <CimSession[]>] [-Credential <PSCredential[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SwitchObject_NetAdapterInterfaceDescription
```
Set-VMSwitchTeam [-ComputerName <String[]>] [-VMSwitch] <VMSwitch[]>
 [-NetAdapterInterfaceDescription <String[]>] [-TeamingMode <VMSwitchTeamingMode>]
 [-LoadBalancingAlgorithm <VMSwitchLoadBalancingAlgorithm>] [-Passthru] [-CimSession <CimSession[]>]
 [-Credential <PSCredential[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SwitchObject_NetAdapterName
```
Set-VMSwitchTeam [-ComputerName <String[]>] [-VMSwitch] <VMSwitch[]> [-NetAdapterName <String[]>]
 [-TeamingMode <VMSwitchTeamingMode>] [-LoadBalancingAlgorithm <VMSwitchLoadBalancingAlgorithm>] [-Passthru]
 [-CimSession <CimSession[]>] [-Credential <PSCredential[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-VMSwitchTeam** cmdlet configures a virtual switch team.

## EXAMPLES

### Example 1: Configure a switch team to user dynamic load balancing
```
PS C:\> Set-VMSwitchTeam -Name "SwitchTeam07" -LoadBalancingAlgorithm Dynamic
```

This command configures the switch team named SwitchTeam07 to use a dynamic load balancing algorithm.

## PARAMETERS

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies one or more Hyper-V hosts that run this cmdlet.
NetBIOS names, IP addresses, and fully qualified domain names are allowable.
The default is the local computer.
Use localhost or a dot (.) to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: PSComputerName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -Credential
Specifies one or more user accounts that have permission to perform this action.
The default is the current user.

```yaml
Type: PSCredential[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LoadBalancingAlgorithm
Specifies the load balancing algorithm that this switch team uses.
The acceptable values for this parameter are: Dynamic and HyperVPort.
The default value is Dynamic.

```yaml
Type: VMSwitchLoadBalancingAlgorithm
Parameter Sets: (All)
Aliases:
Accepted values: HyperVPort, Dynamic

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies an array of names of virtual switches that this cmdlet configures for teaming.

```yaml
Type: String[]
Parameter Sets: SwitchName_NetAdapterName, SwitchName_NetAdapterInterfaceDescription
Aliases: SwitchName

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NetAdapterInterfaceDescription
Specifies an array of interface descriptions of the virtual network adapters that this cmdlet includes in the switch team.
This value replaces the existing members.

```yaml
Type: String[]
Parameter Sets: SwitchName_NetAdapterInterfaceDescription, SwitchObject_NetAdapterInterfaceDescription
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NetAdapterName
Specifies an array of names of the virtual network adapters that this cmdlet includes in the switch team.
This value replaces the existing members.

```yaml
Type: String[]
Parameter Sets: SwitchName_NetAdapterName, SwitchObject_NetAdapterName
Aliases: InterfaceAlias

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Passthru
Indicates that this cmdlet returns the **Microsoft.HyperV.PowerShell.VMSwitch** object that it configures.

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

### -TeamingMode
Specifies the teaming mode.
Currently, the only option is SwitchIndependent.

```yaml
Type: VMSwitchTeamingMode
Parameter Sets: (All)
Aliases:
Accepted values: SwitchIndependent

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMSwitch
Specifies an array of virtual switches that this cmdlet configures for teaming.
To obtain a **VMSwitch** object, use the **Get-VMSwitch** cmdlet.

```yaml
Type: VMSwitch[]
Parameter Sets: SwitchObject_NetAdapterInterfaceDescription, SwitchObject_NetAdapterName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
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

## OUTPUTS

### Microsoft.HyperV.PowerShell.VMSwitch
This cmdlet returns a **VMSwitch** object, if you specify the **Passthru** parameter.

## NOTES

## RELATED LINKS

[Get-VMSwitchTeam](./Get-VMSwitchTeam.md)

[Get-VMSwitch](./Get-VMSwitch.md)

