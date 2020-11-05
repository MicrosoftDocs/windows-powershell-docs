---
external help file: MSFT_NetLbfoTeamNic.cdxml-help.xml
Module Name: NetLbfo
online version: 
schema: 2.0.0
title: Remove-NetLbfoTeamNic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: A7C1AB76-C6E0-4C3E-AAA7-031B3475236A
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Remove-NetLbfoTeamNic

## SYNOPSIS
Removes a team interface from a NIC team.

## SYNTAX

### ByTeamAndVlanID
```
Remove-NetLbfoTeamNic [-Team] <String[]> [-VlanID] <UInt32[]> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject (cdxml)
```
Remove-NetLbfoTeamNic -InputObject <CimInstance[]> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-NetLbfoTeamNic** cmdlet removes a team interface from the NIC team.
The name of a team interface is the team name followed by the VLAN value of this team interface.
You can identify a team interface either by its name, its associated VLAN ID, or its default property.

This cmdlet does not remove the team interface created when the team was created.
To remove the team interface created when the team was created, you must remove the team by using the Remove-NetLbfoTeam cmdlet.

You need administrator privileges to use **Remove-NetLbfoTeamNic**.

## EXAMPLES

### Example 1: Remove a team interface
```
PS C:\>Remove-NetLbfoTeamNIC -Team "Team1 - VLAN 42"
```

This command removes a team interface named Team1 - VLAN 42 from the team "Team1".

## PARAMETERS

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

### -InputObject
Specifies the object which contains the team interface to remove.

```yaml
Type: CimInstance[]
Parameter Sets: InputObject (cdxml)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### -Team
Specifies the name of the NIC team from which to remove the team interface.

```yaml
Type: String[]
Parameter Sets: ByTeamAndVlanID
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -VlanID
Specifies the VLAN ID of the team interface to remove.

```yaml
Type: UInt32[]
Parameter Sets: ByTeamAndVlanID
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None
This cmdlet takes no input objects.

## OUTPUTS

### None
By default, this cmdlet produces no output.

## NOTES

## RELATED LINKS

[Get-NetLbfoTeamNic](./Get-NetLbfoTeamNic.md)

[Set-NetLbfoTeamNic](./Set-NetLbfoTeamNic.md)

[Add-NetLbfoTeamNic](./Add-NetLbfoTeamNic.md)

