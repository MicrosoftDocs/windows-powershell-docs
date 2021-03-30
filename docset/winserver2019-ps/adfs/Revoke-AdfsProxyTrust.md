---
author: Kateyanne
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
Module Name: ADFS
ms.assetid: AE02463D-DF40-4E7F-A92C-E641A8CCB47D
ms.author: v-kaunu
ms.date: 12/20/2016
ms.mktglfcycl: manage
ms.prod: w10
ms.sitesec: library
ms.technology: 
ms.topic: reference
online version: 
schema: 2.0.0
title: Revoke-AdfsProxyTrust
ms.reviewer:
---

# Revoke-AdfsProxyTrust

## SYNOPSIS
Revokes trust for all federation server proxies configured for the Federation Service.

## SYNTAX

```
Revoke-AdfsProxyTrust [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Revoke-AdfsProxyTrust** cmdlet revokes trust for all federation server proxies by resetting the trust ID for the Federation Service.
Use this cmdlet for lockdown purposes in the event of an attack or confirmed possible threat to your deployment.
The cmdlet effectively revokes trust to all configured proxies immediately.

## EXAMPLES

### Example 1: Revoke trust
```
PS C:\> Revoke-AdfsProxyTrust
```

This command revokes all trust between the current federation server and any of its configured federation server proxies.

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
* Use this cmdlet only in the event of a security breach in a live deployment. We recommend that, if you want to practice using this cmdlet, you use a test lab environment.

## RELATED LINKS

