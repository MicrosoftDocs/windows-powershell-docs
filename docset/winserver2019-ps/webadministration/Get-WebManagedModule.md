---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/webadministration/get-webmanagedmodule?view=windowsserver2019-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WebManagedModule
---

# Get-WebManagedModule

## SYNOPSIS
Gets the managed modules that are configured for a particular application.

## SYNTAX

```
Get-WebManagedModule [[-Name] <String>] [-Location <String[]>] [[-PSPath] <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-WebManagedModule** cmdlet gets the managed modules that are configured for a particular application.

## EXAMPLES

### Example 1: Get modules for the default website
```
IIS:\> Get-WebManagedModule -PSPath "IIS:\sites\Default Web Site"
```

This command gets configuration information for modules configured for the default website.

## PARAMETERS

### -Location
Specifies the configuration location from which the cmdlet retrieves configuration information.

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
Specifies the name of the managed module.

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

[New-WebManagedModule](./New-WebManagedModule.md)

[Remove-WebManagedModule](./Remove-WebManagedModule.md)

[Set-WebManagedModule](./Set-WebManagedModule.md)

