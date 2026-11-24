---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/webadministration/new-webapplication?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-WebApplication
---

# New-WebApplication

## SYNOPSIS
Creates an IIS web application.

## SYNTAX

```
New-WebApplication [-Site <String>] [-Name] <String> [-PhysicalPath <String>] [-ApplicationPool <String>]
 [-Force] [<CommonParameters>]
```

## DESCRIPTION
The **New-WebApplication** cmdlet creates an Internet Information Services (IIS) web application.

## EXAMPLES

### Example 1: Create a web application
```
IIS:\> New-WebApplication -Name "TestApp" -Site "Default Web Site" -PhysicalPath "C:\Test" -ApplicationPool "DefaultAppPool"
```

This command creates a web application named TestApp on the default website.
The application files are stored in the C:\Test folder, and the application runs in the DefaultAppPool application pool.

## PARAMETERS

### -ApplicationPool
Specifies the name of the application pool in which the new web application runs.

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
Forces the creation of the application without prompting for user confirmation.

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
Specifies the name of the web application to create.

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
Specifies the physical path to the web application files.

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
Specifies the name of the site on which this cmdlet creates an application.

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

[ConvertTo-WebApplication](./ConvertTo-WebApplication.md)

[Get-WebApplication](./Get-WebApplication.md)

[Remove-WebApplication](./Remove-WebApplication.md)

