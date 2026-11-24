---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hyper-v/remove-vmswitchteammember?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-VMSwitchTeamMember
---

# Remove-VMSwitchTeamMember

## SYNOPSIS
Removes a member from a virtual machine switch team.

## SYNTAX

### SwitchName_NetAdapterName (Default)
```
Remove-VMSwitchTeamMember [-ComputerName <String[]>] [-VMSwitchName] <String[]> [-NetAdapterName <String[]>]
 [-Passthru] [-CimSession <CimSession[]>] [-Credential <PSCredential[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### SwitchName_NetAdapterInterfaceDescription
```
Remove-VMSwitchTeamMember [-ComputerName <String[]>] [-VMSwitchName] <String[]>
 [-NetAdapterInterfaceDescription <String[]>] [-Passthru] [-CimSession <CimSession[]>]
 [-Credential <PSCredential[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SwitchObject_NetAdapterInterfaceDescription
```
Remove-VMSwitchTeamMember [-ComputerName <String[]>] [-VMSwitch] <VMSwitch[]>
 [-NetAdapterInterfaceDescription <String[]>] [-Passthru] [-CimSession <CimSession[]>]
 [-Credential <PSCredential[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SwitchObject_NetAdapterName
```
Remove-VMSwitchTeamMember [-ComputerName <String[]>] [-VMSwitch] <VMSwitch[]> [-NetAdapterName <String[]>]
 [-Passthru] [-CimSession <CimSession[]>] [-Credential <PSCredential[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-VMSwitchTeamMember** cmdlet removes virtual network adapters from a virtual machine switch team.

## EXAMPLES

### Example 1: Remove network adapters from a switch team
```
PS C:\> $VMSwitch = Get-VMSwitch -Name "Switch03"
PS C:\> Remove-VMSwitchTeamMember -VMSwitch $VMSwitch -NetAdapterName "Adapter01","Adapter04"
```

The first command gets the virtual switch named Switch03, and then stores that object in the **$VMSwitch** variable.

The second command removes the network adapters named Adapter01 and Adapter04 as team members from the switch in **$VMSwitch**.

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

### -NetAdapterInterfaceDescription
Specifies an array of interface descriptions of virtual network adapters that this cmdlet removes from a switch team.

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
Specifies an array of names of virtual network adapters that this cmdlet removes from a switch team.

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
Indicates that this cmdlet returns the **Microsoft.HyperV.PowerShell.VMSwitch** object that it modifies.

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

### -VMSwitch
Specifies an array of virtual switches from which this cmdlet removes network adapters.
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

### -VMSwitchName
Specifies an array of names of virtual switches from which this cmdlet removes network adapters.

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

### Microsoft.HyperV.PowerShell.VMSwitch[]
This cmdlet returns an array of **VMSwitch** objects, if you specify the **Passthru** parameter.

## NOTES

## RELATED LINKS

[Add-VMSwitchTeamMember](./Add-VMSwitchTeamMember.md)

[Get-VMSwitch](./Get-VMSwitch.md)

