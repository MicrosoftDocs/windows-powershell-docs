---
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
online version: 
schema: 2.0.0
title: New-WebVirtualDirectory
description: 
keywords: powershell, cmdlet
author: andreabarr
manager: jasgro
ms.date: 2017-10-30
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 7BC49A0B-D4DE-4351-8FC8-FB93946E98E4
ms.author: v-anbarr
ms.reviewer: brianlic
---

# New-WebVirtualDirectory

## SYNOPSIS
Creates a virtual directory in IIS.

## SYNTAX

```
New-WebVirtualDirectory [-Site <String>] [-Application <String>] [-Name] <String> [-PhysicalPath <String>]
 [-Force] [<CommonParameters>]
```

## DESCRIPTION
The **New-WebVirtualDirectory** cmdlet creates a virtual directory in Internet Information Services (IIS).

## EXAMPLES

### Example 1: Creating a virtual directory
```
IIS:\>New-WebVirtualDirectory -Site "Default Web Site" -Name "ContosoVDir" -PhysicalPath "c:\inetpub\contoso"
```

This command creates a virtual directory named ContosoVDir on the default website.

## PARAMETERS

### -Application
Specifies the name of a web application under which this cmdlet creates the virtual directory.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Specifies the name of the new virtual directory.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PhysicalPath
Specifies the physical path to the folder in which this cmdlet creates the virtual directory.
The specified folder must already exist.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Site
Specifies the name of the site under which this cmdlet creates the virtual directory.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WebVirtualDirectory](./Get-WebVirtualDirectory.md)

[Remove-WebVirtualDirectory](./Remove-WebVirtualDirectory.md)

