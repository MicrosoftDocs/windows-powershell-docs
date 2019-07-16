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
title: Import-RDPersonalSessionDesktopAssignment
ms.reviewer:
ms.assetid: 9D7F86ED-3611-4CF5-BAFB-2338701EBE8C
---

# Import-RDPersonalSessionDesktopAssignment

## SYNOPSIS
Imports a map of personal session desktops to users.

## SYNTAX

```
Import-RDPersonalSessionDesktopAssignment [-CollectionName] <String> -path <String>
 [-ConnectionBroker <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Import-RDPersonalSessionDesktopAssignment** cmdlet imports a map of personal session desktops to users.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -CollectionName
Specifies the name of a personal session desktop collection.

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
If you do not specify a value, the cmdlet uses the fully qualified domain name (FQDN) of the local computer.

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

### -path


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

## NOTES

## RELATED LINKS

[Get-RDPersonalSessionDesktopAssignment](./Get-RDPersonalSessionDesktopAssignment.md)

[Export-RDPersonalSessionDesktopAssignment](./Export-RDPersonalSessionDesktopAssignment.md)

[Remove-RDPersonalSessionDesktopAssignment](./Remove-RDPersonalSessionDesktopAssignment.md)

[Set-RDPersonalSessionDesktopAssignment](./Set-RDPersonalSessionDesktopAssignment.md)

