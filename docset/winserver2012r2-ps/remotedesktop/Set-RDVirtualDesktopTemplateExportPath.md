---
external help file: 
Module Name: RemoteDesktop
online version: 
schema: 2.0.0
title: Set-RDVirtualDesktopTemplateExportPath
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: DDF51743-1464-454B-959C-75E36777F50F
ms.author: v-kaunu
ms.reviewer: brianlic
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

This command sets the export path for virtual desktop templates to "\\\\rdsh-1\export".

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Null
None.

## NOTES

## RELATED LINKS

[Get-RDVirtualDesktopTemplateExportPath](./Get-RDVirtualDesktopTemplateExportPath.md)

