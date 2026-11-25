---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hyper-v/get-vmswitchteam?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-VMSwitchTeam
---

# Get-VMSwitchTeam

## SYNOPSIS
Gets virtual switch teams from Hyper-V hosts.

## SYNTAX

### Name (Default)
```
Get-VMSwitchTeam [[-Name] <String>] [-CimSession <CimSession[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential[]>] [<CommonParameters>]
```

### SwitchObject
```
Get-VMSwitchTeam [[-VMSwitch] <VMSwitch[]>] [-CimSession <CimSession[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-VMSwitchTeam** cmdlet gets virtual switch teams from one or more Hyper-V hosts.

## EXAMPLES

### Example 1: Get a switch team
```
PS C:\> Get-VMSwitchTeam -Name "SwitchTeam07"
```

This command retrieves information and team members that belong to the switch team named SwitchTeam07.

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
Aliases:

Required: False
Position: Named
Default value: None
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

### -Name
Specifies the name of the virtual switch team that this cmdlet gets.

```yaml
Type: String
Parameter Sets: Name
Aliases: SwitchName

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMSwitch


```yaml
Type: VMSwitch[]
Parameter Sets: SwitchObject
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.HyperV.Powershell.VMSwitchTeam
This cmdlet returns a **VMSwitchTeam** object.

## NOTES

## RELATED LINKS

[Set-VMSwitchTeam](./Set-VMSwitchTeam.md)

