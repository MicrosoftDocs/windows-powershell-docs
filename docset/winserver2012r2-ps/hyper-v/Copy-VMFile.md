---
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
Module Name: Hyper-V
online version: 
schema: 2.0.0
title: Copy-VMFile
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 41BE782E-40FE-45A0-A233-7F21D46CFFB9
---

# Copy-VMFile

## SYNOPSIS
Copies a file to a virtual machine.

## SYNTAX

### Name (Default)
```
Copy-VMFile [-ComputerName <String[]>] [-Name] <String[]> [-SourcePath] <String> [-DestinationPath] <String>
 -FileSource <CopyFileSourceType> [-Force] [-CreateFullPath] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### VMObject
```
Copy-VMFile [-SourcePath] <String> [-DestinationPath] <String> -FileSource <CopyFileSourceType> [-Force]
 [-CreateFullPath] [-AsJob] [-VM] <VirtualMachine[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Copy-VMFile** cmdlet copies a file to a virtual machine.

## EXAMPLES

### Example 1
```
PS C:\> Copy-VMFile "Test VM" -SourcePath "D:\Test.txt" -DestinationPath "C:\Temp\Test.txt" -CreateFullPath -FileSource Host
```

This example copies the file "test.txt" from the host operating system into the guest operating system of the virtual machine "Test VM".
It will create the directory "C:\Temp" inside the guest operating system if it does not exist already.

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

### -ComputerName
Specifies an array of Hyper-V hosts.
The cmdlet copies the file to the hosts you specify.

```yaml
Type: String[]
Parameter Sets: Name
Aliases: 

Required: False
Position: Named
Default value: .
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

### -CreateFullPath
Indicates that when the cmdlet copies a file, it creates folders if the folder does not already exist.

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

### -DestinationPath
Specifies a path.
The cmdlet copies the file to the destination path.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FileSource
Specifies the type of a file source.

```yaml
Type: CopyFileSourceType
Parameter Sets: (All)
Aliases: 
Accepted values: Host

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Forces the command to run without asking for user confirmation.

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
Specifies an array of virtual machine objects by name.
The cmdlet copies files to the virtual machines you specify.

```yaml
Type: String[]
Parameter Sets: Name
Aliases: VMName

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourcePath
Specifies a path.
The cmdlet copies the file from the source path.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VM
Specifies an array of virtual machine objects.
The cmdlet copies files to the virtual machines you specify.
To obtain a virtual machine object, use the Get-VM cmdlet.

```yaml
Type: VirtualMachine[]
Parameter Sets: VMObject
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

