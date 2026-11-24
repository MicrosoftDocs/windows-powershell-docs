---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/webadministration/new-webvirtualdirectory?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-WebVirtualDirectory
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

### Example 1: Create a virtual directory
```
IIS:\> New-WebVirtualDirectory -Site "Default Web Site" -Name "ContosoVDir" -PhysicalPath "c:\inetpub\contoso"
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WebVirtualDirectory](./Get-WebVirtualDirectory.md)

[Remove-WebVirtualDirectory](./Remove-WebVirtualDirectory.md)

