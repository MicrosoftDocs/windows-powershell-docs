---
ms.technology: 
ms.mktglfcycl: manage
ms.author: v-kaunu
ms.prod: w10
ms.sitesec: library
author: Kateyanne
description: Use this topic to help manage MDOP technologies with Windows PowerShell.
external help file: Microsoft.MBAM.Server.Commands.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro 
ms.assetid: CAFA787C-7974-4162-B8A7-EF45D29A9DB3
ms.date: 12/05/2016
ms.devlang: powershell
ms.topic: reference
online version: 
schema: 2.0.0
title: Disable-MbamWebApplication
ms.reviewer:
---

# Disable-MbamWebApplication

## SYNOPSIS
Disables a web application.

## SYNTAX

### ParameterSetAdministrationPortal
```
Disable-MbamWebApplication [-Force] [-AdministrationPortal] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ParameterSetAgentService
```
Disable-MbamWebApplication [-Force] [-AgentService] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ParameterSetSelfServicePortal
```
Disable-MbamWebApplication [-Force] [-SelfServicePortal] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Disable-MbamWebApplication** cmdlet disables a Microsoft BitLocker Administration and Monitoring (MBAM) web application.
This cmdlet removes any website files that the **Enable-MbamWebApplication** cmdlet installed when you enabled the application.

## EXAMPLES

### Example 1: Disable Administration and Monitoring Website
```
PS C:\> Disable-MbamWebApplication -AdministrationPortal
Are you sure you want to perform this action?
Performing operation "Disable MBAM Web Application (AdministrationPortal) feature"
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):
```

This command disables the Administration and Monitoring Portal feature.
The cmdlet prompts you to confirm the operation.

### Example 2: Disable the Self-Service Portal
```
PS C:\> Disable-MbamWebApplication -SelfServicePortal -Force
```

This command disables the Self-Service Portal feature.
The command specifies the *Force* parameter, and, therefore, the cmdlet does not prompt you to confirm the operation.

### Example 3: Disable Agent Services
```
PS C:\> Disable-MbamWebApplication -AgentService
Are you sure you want to perform this action?
Performing operation "Disable MBAM Web Application (AgentService) feature"
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):
```

This command disables the Agent Services feature.
The cmdlet prompts you to confirm the operation.

## PARAMETERS

### -AdministrationPortal
Indicates that this cmdlet acts on the Administration and Monitoring Website web application.

```yaml
Type: SwitchParameter
Parameter Sets: ParameterSetAdministrationPortal
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AgentService
Indicates that this cmdlet acts on the Agent Services web application.

```yaml
Type: SwitchParameter
Parameter Sets: ParameterSetAgentService
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -Force
Forces the command to run without asking for user confirmation.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SelfServicePortal
Indicates that this cmdlet acts on the Self-Service Portal web application.

```yaml
Type: SwitchParameter
Parameter Sets: ParameterSetSelfServicePortal
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Enable-MbamWebApplication](enable-mbamwebapplication.md)

[Get-MbamWebApplication](get-mbamwebapplication.md)

[Test-MbamWebApplication](test-mbamwebapplication.md)


