---
author: brianlic
description: 
external help file: 
keywords: powershell, cmdlet
manager: alanth
ms.date: 2016-12-20
ms.prod: powershell
ms.technology: powershell
ms.topic: reference
online version: 
schema: 2.0.0
title: Set-RDPersonalSessionDesktopAssignment
ms.assetid: 590F065D-B52F-4618-AF1A-DA3EAD820765
---

# Set-RDPersonalSessionDesktopAssignment

## SYNOPSIS
Associates a personal session desktop assignment with a user.

## SYNTAX

```
Set-RDPersonalSessionDesktopAssignment [-CollectionName] <String> -User <String> -Name <String>
 [-ConnectionBroker <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-RDPersonalSessionDesktopAssignment** cmdlet associates a personal session desktop assignment with a user.

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

### -Name
Specifies the name of the personal session desktop assignment to set.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -User
Specifies a user account in DOMAIN\user format.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-RDPersonalSessionDesktopAssignment](./Get-RDPersonalSessionDesktopAssignment.md)

[Export-RDPersonalSessionDesktopAssignment](./Export-RDPersonalSessionDesktopAssignment.md)

[Import-RDPersonalSessionDesktopAssignment](./Import-RDPersonalSessionDesktopAssignment.md)

[Remove-RDPersonalSessionDesktopAssignment](./Remove-RDPersonalSessionDesktopAssignment.md)

