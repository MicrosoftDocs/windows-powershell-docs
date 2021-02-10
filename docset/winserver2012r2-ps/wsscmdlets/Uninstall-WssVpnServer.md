---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Uninstall-WssVpnServer
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 79BF1EAA-BAFC-4400-880A-55CC59A95FD3
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Uninstall-WssVpnServer

## SYNOPSIS
Uninstalls a VPN server.

## SYNTAX

```
Uninstall-WssVpnServer [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Uninstall-WssVpnServer** cmdlet uninstalls a VPN server on sbs_sbs8_2 server.

## EXAMPLES

### Example 1: Uninstall a VPN server
```
PS C:\> Uninstall-WssVpnServer
```

This command uninstalls a VPN server.

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

## OUTPUTS

## NOTES

## RELATED LINKS

[Install-WssVpnServer](./Install-WssVpnServer.md)

[Test-WssVpnServerInstallation](./Test-WssVpnServerInstallation.md)

