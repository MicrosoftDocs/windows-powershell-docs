---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/webadministration/get-webvirtualdirectory?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WebVirtualDirectory
---

# Get-WebVirtualDirectory

## SYNOPSIS
Gets a list of the virtual directories on the specified site.

## SYNTAX

```
Get-WebVirtualDirectory [-Site <String>] [-Application <String>] [[-Name] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-WebVirtualDirectory** cmdlet gets a list of the virtual directories on the specified site.

## EXAMPLES

### Example 1: Getting a virtual directory
```
IIS:\> Get-WebVirtualDirectory -Site "Default Web Site" -Application "TestApp"
```

This command returns the list of virtual directories on the default website on which the application named TestApp is configured.

## PARAMETERS

### -Application
Specifies the name of a web application associated with virtual directories to return.

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

### -Name
Specifies the name of a virtual directory that this cmdlet returns.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Site
Specifies the name of the site for which this cmdlet returns a list of virtual directories.

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

[New-WebVirtualDirectory](./New-WebVirtualDirectory.md)

[Remove-WebVirtualDirectory](./Remove-WebVirtualDirectory.md)

