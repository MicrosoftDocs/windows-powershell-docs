---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.RightsManagementServices.Admin.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Uninstall-RmsMfgSupport
ms.reviewer:
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
The **Uninstall-RmsMfgSupport** cmdlet removes Microsoft Federation Gateway support from an Active Directory Rights Management Services (AD RMS) server.

## EXAMPLES

### Example 1: Force removal of Microsoft Federation Gateway support
```
PS C:\> Uninstall-RmsMfgSupport -Force
```

This command forces removal of Microsoft Federation Gateway support for AD RMS.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### None

## NOTES
* Before uninstalling Service Pack 1 for Windows Server® 2008 R2, you must remove Microsoft Federation Gateway Support from the AD RMS cluster. Failure to do this may cause an inconsistent configuration of your AD RMS cluster.

## RELATED LINKS

[Using Windows PowerShell with AD RMS](http://go.microsoft.com/fwlink/?LinkId=136806)

[Install-RmsMfgSupport](./Install-RmsMfgSupport.md)

