---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/27/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Remove-WebApplication
ms.reviewer:
ms.assetid: 59096265-31B1-4338-BBBD-D998D1F0435C
---

# Remove-WebApplication

## SYNOPSIS
Removes a web application from an IIS website.

## SYNTAX

```
Remove-WebApplication [-Site <String>] [-Name] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-WebApplication** cmdlet removes a web application from an Internet Information Services (IIS) website.

## EXAMPLES

### Example 1: Add a web application and remove it
```
IIS:\> New-WebApplication -Name "TestApp" -Site "Default Web Site" -PhysicalPath "$Env:systemdrive\inetpub\TestApp" ; "Sleep for 5 seconds before Web App is removed" ; Sleep 5 
IIS:\> Remove-WebApplication -Name "TestApp" -Site "Default Web Site"
```

This first command creates a web application named TestApp on the default website.
The second command removes the application after 5 seconds.

## PARAMETERS

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

### -Name
Specifies the name of the application to remove from the site.

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

### -Site
Specifies the name of the site from which this cmdlet removes the application.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[ConvertTo-WebApplication](./ConvertTo-WebApplication.md)

[Get-WebApplication](./Get-WebApplication.md)

[New-WebApplication](./New-WebApplication.md)

