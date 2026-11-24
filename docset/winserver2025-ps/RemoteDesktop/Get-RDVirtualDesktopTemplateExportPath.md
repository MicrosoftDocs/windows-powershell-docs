---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: RemoteDesktop.psm1-help.xml
Module Name: RemoteDesktop
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/RemoteDesktop/get-rdvirtualdesktoptemplateexportpath?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-RDVirtualDesktopTemplateExportPath
---

# Get-RDVirtualDesktopTemplateExportPath

## SYNOPSIS
Gets the export path setting of the virtual desktop template.

## SYNTAX

```
Get-RDVirtualDesktopTemplateExportPath [[-ConnectionBroker] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-RDVirtualDesktopTemplateExportPath** cmdlet gets the export path setting of the template that Remote Desktop Services uses to deploy virtual machine-based desktops.

## EXAMPLES

### Example 1: Get the export path of the virtual desktop template
```
PS C:\> Get-RDVirtualDesktopTemplateExportPath
```

This command gets the export path setting of the virtual desktop template for the local computer.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Set-RDVirtualDesktopTemplateExportPath](./Set-RDVirtualDesktopTemplateExportPath.md)

[Update-RDVirtualDesktopCollection](./Update-RDVirtualDesktopCollection.md)

