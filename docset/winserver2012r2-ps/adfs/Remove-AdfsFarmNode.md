---
external help file: Microsoft.IdentityServer.Deployment.dll-Help.xml
Module Name: ADFS
online version: 
schema: 2.0.0
title: Remove-AdfsFarmNode
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: F5FA802A-119E-498E-B99D-9E55F51EDEB8
---

# Remove-AdfsFarmNode

## SYNOPSIS
The Remove-AdfsFarmNode cmdlet is deprecated.
Instead, use the Uninstall-WindowsFeature cmdlet.

## SYNTAX

### ADFSRemoveFarmNodeDefault (Default)
```
Remove-AdfsFarmNode -ServiceAccountCredential <PSCredential> [<CommonParameters>]
```

### AdfsRemoveFarmNodeGmsa
```
Remove-AdfsFarmNode -GroupServiceAccountIdentifier <String> [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AdfsFarmNode** cmdlet is deprecated in this release.
Instead, use the Uninstall-WindowsFeaturehttp://go.microsoft.com/fwlink/?LinkID=287572 cmdlet.
For more information on the **Uninstall-WindowsFeature** cmdlet, type `Get-Help Uninstall-WindowsFeature`.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -Credential
```yaml
Type: PSCredential
Parameter Sets: AdfsRemoveFarmNodeGmsa
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GroupServiceAccountIdentifier
```yaml
Type: String
Parameter Sets: AdfsRemoveFarmNodeGmsa
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServiceAccountCredential
```yaml
Type: PSCredential
Parameter Sets: ADFSRemoveFarmNodeDefault
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

[Uninstall-WindowsFeature](https://go.microsoft.com/fwlink/?LinkID=287572)

