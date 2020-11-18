---
external help file: 
Module Name: RemoteDesktop
online version: 
schema: 2.0.0
title: Export-RDPersonalVirtualDesktopAssignment
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 7FF9BC8D-6EF3-478F-8C74-92329A29C46D
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Export-RDPersonalVirtualDesktopAssignment

## SYNOPSIS
Exports the current associations between users and personal virtual desktops to a file.

## SYNTAX

```
Export-RDPersonalVirtualDesktopAssignment [-CollectionName] <String> -Path <String>
 [-ConnectionBroker <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Export-RDPersonalVirtualDesktopAssignment** cmdlet exports the current associations between users and personal virtual desktops to a text file.

## EXAMPLES

### Example1: Create a delimited text file of the current associations between users and personal virtual desktops
```
PS C:\> Export-RDPersonalVirtualDesktopAssignment -Path "c:\reports\VirtDeskAssignReport" -ConnectionBroker "Rdcb.Contoso.com"
```

This command creates a text file in the path named c:\reports\VirtDeskAssignReport by using the RD Connection Broker server named Rdcb.Contoso.com.

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
Specifies the Remote Desktop Connection Broker (RD Connection Broker) server for this Remote Desktop deployment.
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
Specifies the path and file name of an output file.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Get-RDPersonalVirtualDesktopAssignment](./Get-RDPersonalVirtualDesktopAssignment.md)

[Import-RDPersonalVirtualDesktopAssignment](./Import-RDPersonalVirtualDesktopAssignment.md)

[Remove-RDPersonalVirtualDesktopAssignment](./Remove-RDPersonalVirtualDesktopAssignment.md)

[Set-RDPersonalVirtualDesktopAssignment](./Set-RDPersonalVirtualDesktopAssignment.md)

