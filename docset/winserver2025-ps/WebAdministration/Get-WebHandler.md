---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/webadministration/get-webhandler?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WebHandler
---

# Get-WebHandler

## SYNOPSIS
Gets IIS request handlers.

## SYNTAX

```
Get-WebHandler [[-Name] <String>] [-Location <String[]>] [[-PSPath] <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-WebHandler** cmdlet gets Internet Information Services (IIS) request handlers.
If you specify the *Name* parameter, information is returned for the specified handler.

## EXAMPLES

### Example 1: Get the handler section
```
IIS:\> Get-WebHandler -PSPath "IIS:\Sites\Default Web Site"
```

This command gets handlers configured for the default website.

## PARAMETERS

### -Location
Specifies the location for which the cmdlet returns handler information.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of a handler to get.

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

### -PSPath
Specifies an IIS configuration path.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
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

[New-WebHandler](./New-WebHandler.md)

[Remove-WebHandler](./Remove-WebHandler.md)

[Set-WebHandler](./Set-WebHandler.md)

