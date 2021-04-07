---
author: Kateyanne
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: ProcessMitigations.dll-Help.xml
manager: jasgro
Module Name: ProcessMitigations
ms.author: v-kaunu
ms.date: 03/29/2017
ms.mktglfcycl: manage
ms.prod: w10
ms.reviewer: 
ms.sitesec: library
ms.technology: 
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/processmitigations/get-processmitigation?view=windowsserver2016-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ProcessMitigation
---

# Get-ProcessMitigation

## SYNOPSIS
Gets the current process mitigation settings, either from the registry, from a running process, or saves all to a XML.

## SYNTAX

### FullPolicySet
```
Get-ProcessMitigation [-FullPolicy] [<CommonParameters>]
```

### IdSet
```
Get-ProcessMitigation [-Id] <Int32[]> [<CommonParameters>]
```

### NameSet
```
Get-ProcessMitigation [-Name] <String> [-RunningProcesses] [<CommonParameters>]
```

### SaveSet
```
Get-ProcessMitigation [-RegistryConfigFilePath <String>] [<CommonParameters>]
```

### SystemSet
```
Get-ProcessMitigation [-System] [<CommonParameters>]
```

## DESCRIPTION
Gets all process mitigation settings either by process name (either running or from -Registry), or by process ID. Can also save all settings to an XML file.

## EXAMPLES

### Example 1
```
PS C:\> Get-ProcessMitigation -Name notepad.exe -RunningProcess
```

Gets the current settings on all running instances of notepad.exe

### Example 2
```
PS C:\> Get-ProcessMitigation -Name notepad.exe
```

Gets the current settings in the registry for notepad.exe

### Example 3
```
PS C:\> Get-ProcessMitigation -Id 1304
```

Gets the current settings for the running process with pid 1304

### Example 4
```
PS C:\> Get-ProcessMitigation -RegistryConfigFilePath settings.xml
```

Gets the all process mitigation settings from the registry and saves them to the xml file settings.xml

### Example 5
```
PS C:\> Get-ProcessMitigation -FullPolicy
```

Gets all policies for all processes set in the registry.

### Example 6
```
PS C:\> Get-ProcessMitigation -System
```

Gets the current system process mitigation defaults stored in the registry.

### Example 7
```
PS C:\> Get-Process notepad | Get-ProcessMitigation
```

Gets the current process mitigation settings for all running instances of notepad.exe

## PARAMETERS

### -FullPolicy
Returns every processes' current mitigation settings in the registry

```yaml
Type: SwitchParameter
Parameter Sets: FullPolicySet
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id
Process Id to retrieve current running process mitigation settings from

```yaml
Type: Int32[]
Parameter Sets: IdSet
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Name
{Current process name to get current running (Or from registry) process mitigation settings from one (Can be more than one instance)

```yaml
Type: String
Parameter Sets: NameSet
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RegistryConfigFilePath
File to save the current registry process mitigation configuration to

```yaml
Type: String
Parameter Sets: SaveSet
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RunningProcess
Pull the current process mitigation settings from a running instance instead of the registry.

```yaml
Type: SwitchParameter
Parameter Sets: NameSet
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -System
Pulls the current system defaults for process mitigations.

```yaml
Type: SwitchParameter
Parameter Sets: SystemSet
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String
System.Int32\[\]

## OUTPUTS

### Microsoft.Samples.PowerShell.Commands.AppMitigations

## NOTES

## RELATED LINKS

