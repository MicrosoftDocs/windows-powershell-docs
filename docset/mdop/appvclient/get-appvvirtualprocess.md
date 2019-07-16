---
ms.technology: powershell-mdop
ms.mktglfcycl: manage
ms.author: v-anbarr
ms.prod: w10
ms.sitesec: library
author: andreabarr
description: Use this topic to help manage MDOP technologies with Windows PowerShell.
external help file: AppVClientCmdlets-help.xml
keywords: powershell, cmdlet
manager: jasgro 
ms.assetid: 124E64C5-DBA8-416B-9DC4-EDABCCFEF6AC
ms.date: 2016-12-05
ms.devlang: powershell
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-AppvVirtualProcess
---

# Get-AppvVirtualProcess

## SYNOPSIS
Displays the virtual processes running on a computer.

## SYNTAX

### Name (Default)
```
Get-AppvVirtualProcess [[-Name] <String[]>] [-ComputerName <String[]>] [-Module] [-FileVersionInfo]
 [<CommonParameters>]
```

### Id
```
Get-AppvVirtualProcess -Id <Int32[]> [-ComputerName <String[]>] [-Module] [-FileVersionInfo]
 [<CommonParameters>]
```

### InputObject
```
Get-AppvVirtualProcess [-ComputerName <String[]>] [-Module] [-FileVersionInfo] -InputObject <Process[]>
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-AppvVirtualProcess** cmdlet displays each of the virtual processes running on a computer.

## EXAMPLES

### Example 1: Display all active virtual processes
```
PS C:\>Get-AppvVirtualProcess
```

This command displays all active virtual processes.

### Example 2: Display file information for a virtual process
```
PS C:\>Get-AppvVirtualProcess -Name "myVirtualProcess" -FileVersionInfo
```

This command displays file information for the process named myVirtualProcess.

### Example 3: Display file information for a virtual process by using the pipeline operator
```
PS C:\>Get-Process -Name "myVirtualProcess" | Get-AppvVirtualProcess -FileVersionInfo
```

## PARAMETERS

### -ComputerName
Specifies the computer name.
Used primarily for viewing processes on different computer.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: Cn

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FileVersionInfo
Indicates that this cmdlet returns the **ProductVersion**, **FileVersion** and un-virtualized **Filename** for each **ProcessName**.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: FV, FVI

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id
Specifies the Virtual Process ID.

```yaml
Type: Int32[]
Parameter Sets: Id
Aliases: PID

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InputObject
{{Fill InputObject Description}}

```yaml
Type: Process[]
Parameter Sets: InputObject
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Module
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

### -Name
Specifies the name of a process, which is also known as the **ProcessName**.

```yaml
Type: String[]
Parameter Sets: Name
Aliases: ProcessName

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.Diagnosis.Process

## OUTPUTS

## NOTES

## RELATED LINKS

[Start-AppvVirtualProcess](./Start-AppvVirtualProcess.md)


