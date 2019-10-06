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
title: Get-RmsSvcAccount
ms.reviewer:
ms.assetid: A49F23B5-487F-43D3-9375-1B04F038E495
---

# Get-RmsSvcAccount

## SYNOPSIS
Gets service account credentials for an Active Directory Rights Management Services (AD RMS) cluster.

## SYNTAX

```
Get-RmsSvcAccount [-Path] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Get-RmsSvcAccount** cmdlet gets service account credentials for an Active Directory Rights Management Services (AD RMS) cluster.

To get the service account credentials, set the *Path* parameter to `<PSDrive>:\` where `<PSDrive>` is the drive ID of the provider drive associated with AD RMS cluster.

## EXAMPLES

### Example 1: Get the service account
```
PS C:\> Get-RmsSvcAccount -Path "."
```

This command displays the AD RMS service account.

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

### -Path
Specifies a provider drive and path or relative path on the current drive.
Use a dot (.) to specify the current location.
This parameter does not accept wildcards and has no default value.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.Management.Automation.PSCredential

## NOTES

## RELATED LINKS

[Using Windows PowerShell with AD RMS](http://go.microsoft.com/fwlink/?LinkId=136806)

[Set-RmsSvcAccount](./Set-RmsSvcAccount.md)

