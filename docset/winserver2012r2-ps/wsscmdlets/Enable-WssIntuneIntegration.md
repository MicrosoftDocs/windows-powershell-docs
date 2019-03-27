---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Enable-WssIntuneIntegration
description: 
keywords: powershell, cmdlet
author: kenwith
manager: jasgro
ms.date: 2017-12-05
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 25702D92-3F70-4682-8C48-35605AE4A0BC
ms.author: kenwith
ms.reviewer: brianlic
---

# Enable-WssIntuneIntegration

## SYNOPSIS
Enable integration between Windows Server Essential and Windows Intune.

## SYNTAX

```
Enable-WssIntuneIntegration [[-IntuneUserName] <String>] [[-Password] <SecureString>] [-Force] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Enable integration between Windows Server Essential and Windows Intune.

## EXAMPLES

### Example 1
```
PS C:\>Enable-WssIntuneIntegration -IntuneUserName admin@wse.onmicrosoft.com -Password xxxxxxx
```

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
Force the Cmdlet operation without confirmation.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IntuneUserName
user's principle name

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Password
user's password

```yaml
Type: SecureString
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
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

## OUTPUTS

## NOTES

## RELATED LINKS

