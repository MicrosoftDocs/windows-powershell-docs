---
author: Kateyanne
description: 
external help file: Microsoft.Assessments.WAS.PowerShell.dll-Help.xml
manager: jasgro
Module Name: WasPSExt
ms.author: v-kaunu
ms.date: 12/05/2017
ms.prod: powershell
ms.reviewer: brianlic
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/waspsext/get-wascomputer?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WASComputer
---

# Get-WASComputer

## SYNOPSIS
Gets a list of available test computers.

## SYNTAX

### ComputerId
```
Get-WASComputer [-ComputerID] <Guid[]> [<CommonParameters>]
```

### ComputerName
```
Get-WASComputer [[-ComputerName] <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-WASComputer** cmdlet gets a list of all the test computers that are in the dep_nextref_was inventory.
The list includes all the computer metadata.

## EXAMPLES

### Example 1: Get all computers
```
PS C:\> Get-WASComputer
```

This command gets all the computers included in the dep_nextref_was inventory.

### Example 2: Get all computers and output the data to a table
```
PS C:\> Get-WASComputer | Format-Table -Property ComputerName,ComputerId,Location,StatusMessage
```

This command gets all the computers and formats the output as a table.

### Example 3: Get all computers that match a specific search string
```
PS C:\> Get-WASComputer *toast | Format-Table -Property ComputerName,ComputerId,Location,StatusMessage
```

This command gets all the computers with a name that matches the search string "toast", and outputs the data to a table.

### Example 4: Get all computers with a specific ID
```
PS C:\> Get-WASComputer -ComputerId d52a668a-a138-48a6-8cdb-000000000000
```

This command gets a computer with a specific ID.

### Example 5: Get all computers containing a specific device
```
PS C:\> $Computers = foreach ($comp in Get-WasComputer) { foreach ($device in $comp.Devices) { if ($device.Name -eq "Broadcom 802.11g Network Adapter") { $comp } } } 
PS C:\> Format-Table -Property ComputerName,ComputerId,Location,StatusMessage -InputObject $computers
```

This command gets all computers that contain a specific device, and formats the output as a table.

### Example 6: Get all computers running an action
```
PS C:\> Get-WASComputer | where {$_.CurrentAction -ne $null} | Format-Table -Property ComputerName,ComputerId,Location
```

This command gets all computers that are currently running an action, and formats the output as a table.

## PARAMETERS

### -ComputerID
Specifies the Windows Assessment Services computer ID for the computer you want to get.
If this parameter is not specified, all computers in the inventory are listed.
You must use the computer ID that is recorded in the Windows Assessment Services inventory, not the computer GUID.

```yaml
Type: Guid[]
Parameter Sets: ComputerId
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies the name of the computer that you want to get.
This is the computer name recorded in the Windows Assessment Services inventory.
This parameter is optional.
You can also specify the computer name without the parameter.
The full name of the computer isn't required.
Wildcards are accepted.

```yaml
Type: String[]
Parameter Sets: ComputerName
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Windows Assessment Services Technical Reference](https://go.microsoft.com/fwlink/?LinkId=215628)

[Reset-WASComputer](./Reset-WASComputer.md)

[Resume-WASComputer](./Resume-WASComputer.md)

[Skip-WASJobInstance](./Skip-WASJobInstance.md)

[Update-WASJob](./Update-WASJob.md)

