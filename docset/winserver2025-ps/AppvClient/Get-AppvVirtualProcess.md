---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: AppVClientCmdlets-help.xml
Module Name: AppvClient
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/appvclient/get-appvvirtualprocess?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
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
The **Get-AppvVirtualProcess** cmdlet displays each of the virtual processes that are running on a computer.

## EXAMPLES

### Example 1: Display all active virtual processes
```
PS C:\> Get-AppvVirtualProcess
```

This command displays all active virtual processes.

### Example 2: Display file information for a virtual process
```
PS C:\> Get-AppvVirtualProcess -Name "myVirtualProcess" -FileVersionInfo
```

This command displays file information for the process named myVirtualProcess.

### Example 3: Display file information for a virtual process by using the pipeline operator
```
PS C:\> Get-Process -Name "myVirtualProcess" | Get-AppvVirtualProcess -FileVersionInfo
```

This command displays file information for the process named myVirtualProcess.

## PARAMETERS

### -ComputerName
Specifies an array of computer names.

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
Specifies the input to this cmdlet.
You can use this parameter, or you can pipe the input to this cmdlet.

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
Specifies a module.

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
Specifies the name of a process, which is also known as **ProcessName**.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.Diagnosis.Process

## OUTPUTS

## NOTES

## RELATED LINKS

[Start-AppvVirtualProcess](./Start-AppvVirtualProcess.md)

