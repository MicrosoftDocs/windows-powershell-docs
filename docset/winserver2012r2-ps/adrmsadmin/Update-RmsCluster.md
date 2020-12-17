---
external help file: Microsoft.RightsManagementServices.Admin.dll-Help.xml
Module Name: ADRMSAdmin
online version: 
schema: 2.0.0
title: Update-RmsCluster
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
ms.assetid: ABF90FFB-2235-4D85-AE24-57462FDC5B8C
---

# Update-RmsCluster

## SYNOPSIS
Updates the Active Directory Rights Management Services (AD RMS) cluster information.

## SYNTAX

```
Update-RmsCluster [-Force] [-Path] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The Update-RmsCluster cmdlet updates the cluster information including the hierarchy of content that defines the cluster in Active Directory Rights Management Services (AD RMS).
The AD RMS cluster hierarchy is reflected in the directory structure of the provider drive associated with the cluster.
For example, you can access the rights policy template information from the RightsPolicyTemplate subdirectory.

To update AD RMS cluster information, set the Path parameter to  \<PSDrive\>:\ where \<PSDrive\> is the AD RMS provider drive ID associated with the cluster that you want to update.

## EXAMPLES

### --------------  EXAMPLE 1 --------------
```
C:\PS>Update-RmsCluster -Path . -Force
```

This command updates the AD RMS cluster information.

## PARAMETERS

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Overrides restrictions that prevent the command from succeeding, just so the changes do not compromise security.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Path
Specifies a provider drive and path or relative path on the current drive.
This parameter is required.
Use a dot (.) to specify the current location.
This parameter does not accept wildcards and has no default value.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: String.empty
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Using Windows PowerShell with AD RMS](https://go.microsoft.com/fwlink/?LinkId=136806)

