---
external help file: ClusterAwareUpdating.dll-Help.xml
Module Name: ClusterAwareUpdating
online version: 
schema: 2.0.0
title: Unregister-CauPlugin
ms.author: v-anbarr
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: andreabarr
manager: jasgro
ms.date: 2017-10-30
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: F0EEF063-A47F-4D06-8BC4-332540CB3877
---

# Unregister-CauPlugin

## SYNOPSIS
Removes a software updating plug-in from the list of plug-ins that are used by Cluster-Aware Updating (CAU).

## SYNTAX

```
Unregister-CauPlugin [-Name] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Unregister-CauPlugin** cmdlet removes a software updating plug-in from the list of plug-ins that are used by Cluster-Aware Updating (CAU).
The plug-in can be removed, but afterwards, it cannot be used for Updating Runs.
The Microsoft.WindowsUpdatePlugin and Microsoft.HotfixPlugin plug-ins, which are installed with CAU, cannot be unregistered.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Unregister-CauPlugin -Name Plugin01
```

This example removes the plug-in named Plugin01 from the list of plug-ins that are used by Cluster-Aware Updating (CAU).

## PARAMETERS

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the plug-in to unregister.

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

### -WhatIf
Shows what would happen if the cmdlet runs. The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.ClusterAwareUpdating.CauPlugin

## NOTES

## RELATED LINKS

[Get-CauPlugin](./Get-CauPlugin.md)

[Register-CauPlugin](./Register-CauPlugin.md)

