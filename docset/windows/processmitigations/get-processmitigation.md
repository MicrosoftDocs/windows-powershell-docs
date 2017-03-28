---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: brianlic
author: brianlic-msft
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: processmitigations.dll-Help.xml
keywords: powershell, cmdlet
manager: alanth
ms.date: 2017-03-29
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-ProcessMitigation
---


# Get-ProcessMitigation

## SYNOPSIS
Gets the current process mitigation settings, either from the registry, from a running process, or saves all to a XML.

## SYNTAX

### NameMode
```
Get-ProcessMitigation [[-Name] <String>] [-Running] [<CommonParameters>]
```

### IdMode
```
Get-ProcessMitigation [[-Id] <Int32[]>] [-Running] [<CommonParameters>]
```

### SaveMode
```
Get-ProcessMitigation [-Save <String>] [<CommonParameters>]
```

## DESCRIPTION
Gets all process mitigation settings either by process name (either running or from -Registry), or by process ID.
Can also save all settings to an XML file.

## EXAMPLES

### Example 1
```
PS C:\> Get-ProcessMitigation -Name notepad.exe -Running
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

Gets the current settings for the running process with Id 1304

### Example 4
```
PS C:\> Get-ProcessMitigation -Save settings.xml
```

Gets the all process mitigation settings from the registry and saves them to the xml file settings.xml

## PARAMETERS

### -Id
Process Id to retrieve current running process mitigation settings from

```yaml
Type: Int32[]
Parameter Sets: IdMode
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Current process name to get current running (Or from registry) process mitigation settings from one (Can be more than one instance)

```yaml
Type: String
Parameter Sets: NameMode
Aliases: n

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Running
Gets the process mitigation settings on a running process -Name instead of from the registry

```yaml
Type: SwitchParameter
Parameter Sets: NameMode
Aliases: r

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: SwitchParameter
Parameter Sets: IdMode
Aliases: r

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Save
Saves all the process mitigation settings in the registry to this file

```yaml
Type: String
Parameter Sets: SaveMode
Aliases: s

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String
System.Int32\[\]

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

