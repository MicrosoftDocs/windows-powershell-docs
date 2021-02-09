---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Uninstall-WssAddIn
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 14DEA680-C4B6-43FD-B49B-CECD615A08E2
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Uninstall-WssAddIn

## SYNOPSIS
Uninstalls an add-in.

## SYNTAX

```
Uninstall-WssAddIn [-Force] [-Id] <Guid> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Uninstall-WssAddIn** cmdlet uninstalls an add-in from the server.
When you uninstall an add-in, the functionality provided by add-in is no longer available on the server.

## EXAMPLES

### Example 1: Uninstall an add-in
```
PS C:\> Uninstall-WssAddIn -Id {6617708D-0F98-4898-8D05-9E882C23DCB2}
```

This command uninstalls the add-in that has the package Id 6617708D-0F98-4898-8D05-9E882C23DCB2.

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

### -Id
Specifies the GUID of an installed package.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
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

[Get-WssAddIn](./Get-WssAddIn.md)

[Install-WssAddIn](./Install-WssAddIn.md)

