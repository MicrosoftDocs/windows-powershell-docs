---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: ClusterAwareUpdating.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Register-CauPlugin
ms.reviewer:
ms.assetid: 8150ACFB-8077-4394-9FF1-3293F28FF32E
---

# Register-CauPlugin

## SYNOPSIS
Registers a CAU software updating plug-in on the local computer.

## SYNTAX

```
Register-CauPlugin [-Path] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Register-CauPlugin** cmdlet registers a Cluster-Aware Updating (CAU) software updating plug-in on the local computer.

CAU always uses a plug-in when performing updates, although you do not need to register a plug-in because CAU uses the **Microsoft.WindowsUpdatePlugin** plug-in by default.
This plug-in communicates with the Windows Update Agent software resident on each node, the same software that is used when updates are downloaded from Windows Update or Microsoft Update, or from a Windows Server Update Services (WSUS) server.
For more information about how plug-ins work in CAU, see [How CAU Plug-ins Work](http://go.microsoft.com/fwlink/p/?LinkId=235333).

## EXAMPLES

### Example 1: Register a specific plug-in located in the specified folder
```
PS C:\> Register-CauPlugin -Path "C:\PluginDevelopment\Plugin01.dll" -Force
```

The command registers a plug-in called Plugin01.dll located in the C:\PluginDevelopment folder.
Because the command specifies the *Force* parameter, the cmdlet runs without displaying confirmation prompts.

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
Specifies the path to the binary that implements the plug-in.
Classes that implement the plug-in interface and are decorated with the plug-in attribute, are discovered through reflection and registered.

```yaml
Type: String
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

### None

## OUTPUTS

### Microsoft.ClusterAwareUpdating.CauPlugin

## NOTES

## RELATED LINKS

[Get-CauPlugin](./Get-CauPlugin.md)

[Unregister-CauPlugin](./Unregister-CauPlugin.md)

