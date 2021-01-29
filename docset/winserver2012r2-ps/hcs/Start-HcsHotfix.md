---
external help file: Microsoft.HCS.Management.dll-Help.xml
online version: 
schema: 2.0.0
title: Start-HcsHotfix
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 4EB82928-D161-4E13-BFDC-8761ADC76411
---

# Start-HcsHotfix

## SYNOPSIS
Installs a hotfix on a StorSimple device.

## SYNTAX

```
Start-HcsHotfix [-Force] [-Credential <PSCredential>] -Path <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Start-HcsHotfix** cmdlet installs a hotfix on a StorSimple device.
You must install maintenance mode updates on each controller individually.
If you do not install a maintenance mode hotfix on each controller, data may become lost or corrupted.

## EXAMPLES

### Example 1: Install a hotfix
```
PS C:\>Start-HcsHotfix -Path "\\myshare\hotfix\hotfix.exe"
```

This command installs a hotfix on a StorSimple device.

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

### -Credential
Specifies a **PSCredential** object.
Specify a credential that has read permission for the location that the **Path** parameter specifies.
To obtain a **PSCredential** object, use the Get-Credentialhttp://go.microsoft.com/fwlink/?LinkID=293936 cmdlet.
For more information, type `Get-Help Get-Credential`.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases: 

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

### -Path
Specifies a file name, including the path, to the hotfix to install.
The hotfix must be on a share that the StorSimple device has access to.
If the share requires credentials, they must be supplied with the **Credential** parameter.

If you have trouble accessing a network share by specifying a name (for example, \\\\mysharehost\temp\\), try accessing it by IP address instead (for example, \\\\192.168.0.25\temp\\).
Because this device is not joined to a domain, accessing network shares by name does not always work, depending on the configuration of your network.
The device cannot communicate over IPSEC enabled networks.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Start-HcsUpdate](./Start-HcsUpdate.md)

