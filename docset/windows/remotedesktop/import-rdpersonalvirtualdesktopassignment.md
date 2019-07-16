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
title: Import-RDPersonalVirtualDesktopAssignment
ms.reviewer:
ms.assetid: FB66E4F3-2B4A-4717-B674-59238F0C5A34
---

# Import-RDPersonalVirtualDesktopAssignment

## SYNOPSIS
Imports associations between user accounts and personal virtual desktops from a text file.

## SYNTAX

```
Import-RDPersonalVirtualDesktopAssignment [-CollectionName] <String> -Path <String>
 [-ConnectionBroker <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Import-RDPersonalVirtualDesktopAssignment** cmdlet imports associations between user accounts and personal virtual desktops from a text file.

## EXAMPLES

### 1: Import a personal virtual desktop assignment
```
PS C:\>Import-RDPersonalVirtualDesktopAssignment -CollectionName "Virtual Desktop Collection" -Path "C:\Import\VirtDeskAssignReport"
```

This command imports a personal virtual desktop assignment from the file named C:\Import\VirtDeskAssignReport.

## PARAMETERS

### -CollectionName
Specifies the name of a personal virtual desktop collection.

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

### -ConnectionBroker
Specifies the Remote Desktop Connection Broker (RD Connection Broker) server for a Remote Desktop deployment.
If you do not supply a value, the cmdlet uses the fully qualified domain name (FQDN) of the local computer.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path
Specifies the path and file name of a file to import.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Export-RDPersonalVirtualDesktopAssignment](./Export-RDPersonalVirtualDesktopAssignment.md)

[Get-RDPersonalVirtualDesktopAssignment](./Get-RDPersonalVirtualDesktopAssignment.md)

[Remove-RDPersonalVirtualDesktopAssignment](./Remove-RDPersonalVirtualDesktopAssignment.md)

[Set-RDPersonalVirtualDesktopAssignment](./Set-RDPersonalVirtualDesktopAssignment.md)

