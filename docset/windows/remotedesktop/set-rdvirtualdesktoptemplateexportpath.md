---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: 
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Set-RDVirtualDesktopTemplateExportPath
ms.reviewer:
ms.assetid: DDF51743-1464-454B-959C-75E36777F50F
---

# Set-RDVirtualDesktopTemplateExportPath

## SYNOPSIS
Sets the export path for virtual desktop templates.

## SYNTAX

```
Set-RDVirtualDesktopTemplateExportPath [[-ConnectionBroker] <String>] [-Path] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Set-RDVirtualDesktopTemplateExportPath** cmdlet sets the path that Remote Desktop Services uses to export virtual desktop templates for the virtual machine-based desktop deployment.

## EXAMPLES

### Example 1: Set the export path for virtual export templates
```
PS C:\> Set-RDVirtualDesktopTemplateExportPath -Path "\\rdsh-1\export"
```

This command sets the export path for virtual desktop templates to \\\\rdsh-1\export.

## PARAMETERS

### -ConnectionBroker
Specifies the Remote Desktop Connection Broker (RD Connection Broker) server for a remote desktop deployment.
If you do not specify a value, the cmdlet uses the fully qualified domain name (FQDN) of the local computer.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path
Specifies the path for exported virtual desktop templates.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Null

## NOTES

## RELATED LINKS

[Get-RDVirtualDesktopTemplateExportPath](./Get-RDVirtualDesktopTemplateExportPath.md)

