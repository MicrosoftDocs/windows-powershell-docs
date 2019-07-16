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
title: Install-RmsMfgSupport
ms.reviewer:
ms.assetid: CE19107A-D9E3-4919-B4D7-26F1506E213E
---

# Install-RmsMfgSupport

## SYNOPSIS
Adds Microsoft Federation Gateway support to an AD RMS server.

## SYNTAX

```
Install-RmsMfgSupport [-Force] [-FederationUrl <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Install-RmsMfgSupport** cmdlet adds Microsoft Federation Gateway support to an Active Directory Rights Management Services (AD RMS) server.

## EXAMPLES

### Example 1: Add Microsoft Federation Gateway support
```
PS C:\> Install-RmsMfgSupport
```

This command adds Microsoft Federation Gateway support to an AD RMS server.

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

### -FederationUrl
Specifies the uniform resource locator (URL) for the AD RMS server to use to connect to the Microsoft Federation Gateway.
If this parameter is not specified, AD RMS connects to the Microsoft Federation Gateway using the default value.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Force
Forces the command to run without asking for user confirmation.

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
* Before adding Microsoft Federation Gateway Support, it is very important that you back up the AD RMS configuration database.
* Do not run this command if the AD RMS snap-in is open in the Microsoft Management Console (MMC). If you do, the command will not respond until you close the AD RMS MMC snap-in.
* Before uninstalling Service Pack 1 for Windows® 7, you must remove Microsoft Federation Gateway Support from the AD RMS cluster by running the **Uninstall-RmsMfgSupport** cmdlet. Failure to do so may cause an inconsistent configuration of your AD RMS cluster.

## RELATED LINKS

[Using Windows PowerShell with AD RMS](http://go.microsoft.com/fwlink/?LinkId=136806)

