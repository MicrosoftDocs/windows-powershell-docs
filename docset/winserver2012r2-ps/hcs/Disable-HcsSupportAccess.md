---
external help file: Microsoft.HCS.Management.dll-Help.xml
online version: 
schema: 2.0.0
title: Disable-HcsSupportAccess
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 8B3014DD-D180-4C33-A259-0F31BEE36AAC
---

# Disable-HcsSupportAccess

## SYNOPSIS
Disables support access to this device.

## SYNTAX

```
Disable-HcsSupportAccess [-Scope <ClusterScope>] [<CommonParameters>]
```

## DESCRIPTION
The **Disable-HcsSupportAccess** cmdlet disables access to this device for Microsoft Customer Service and Support.
This cmdlet does not close any currently active support sessions.

## EXAMPLES

### Example 1: Disable support access
```
PS C:\> Disable-HcsSupportAccess
```

This command disables support access for your device.

## PARAMETERS

### -Scope
Specifies the scope.
The acceptable values for this parameter are:

- Cluster.
Disable support access for both nodes.
This is the default. 
- Controller.
Disable support access for the local node only.

```yaml
Type: ClusterScope
Parameter Sets: (All)
Aliases: 
Accepted values: Cluster, Controller

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

###  
This cmdlet does not generate any output.

## NOTES

## RELATED LINKS

[Enable-HcsSupportAccess](./Enable-HcsSupportAccess.md)

[Get-HcsSupportAccess](./Get-HcsSupportAccess.md)

