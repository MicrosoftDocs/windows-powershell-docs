---
external help file: Microsoft.RightsManagementServices.Admin.dll-Help.xml
Module Name: ADRMSAdmin
online version: 
schema: 2.0.0
title: Uninstall-RmsMfgSupport
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 559C4856-F2A2-411C-A41F-B1B079DA1486
---

# Uninstall-RmsMfgSupport

## SYNOPSIS
Removes Microsoft Federation Gateway support from an AD RMS server.

## SYNTAX

```
Uninstall-RmsMfgSupport [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The Uninstall-RmsMfgSupport cmdlet removes Microsoft Federation Gateway support from an AD RMS server.

## EXAMPLES

### --------------  EXAMPLE 1 --------------
```
PS C:\>Uninstall-RmsMfgSupport -Force
```

Forces removal of Microsoft Federation Gateway support for AD RMS.

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
Forces completion of the current operation.

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
* Before uninstalling Service Pack 1 for Windows Server 2008 R2, you must remove Microsoft Federation Gateway Support from the AD RMS cluster. Failure to do this may cause an inconsistent configuration of your AD RMS cluster.

## RELATED LINKS

[Using Windows PowerShell with AD RMS](https://go.microsoft.com/fwlink/?LinkId=136806)

[Install-RmsMfgSupport](./Install-RmsMfgSupport.md)

