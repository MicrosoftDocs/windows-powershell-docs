---
external help file: Wssg.Setup.Commands.dll-Help.xml
online version: 
schema: 2.0.0
title: Remove-WssConfigurationData
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 2EF52BD0-41F2-487B-B9E0-76B552C7DAD2
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Remove-WssConfigurationData

## SYNOPSIS
Removes data, scheduled tasks, and log files and disables the Windows Server Essential Experience role.

## SYNTAX

```
Remove-WssConfigurationData [-ValidateOnly] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-WssConfigurationData** cmdlet removes data, scheduled tasks, and log files that the Windows Server Essential Experience role uses.
After you run this cmdlet, you can then remove the Windows Server Essential Experience role.

## EXAMPLES

### Example 1: Remove configuration data
```
PS C:\> Remove-WssConfigurationData
```

This command removes the configuration data and disables the Windows Server Essential Experience role.

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

### -ValidateOnly
Indicates that the cmdlet validates that the Windows Server Essential Experience role is configured on the target server.
Use this parameter to determine if you must remove the configuration data before you can remove the Windows Server Essential Experience role.

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

### System.Boolean, Microsoft.WindowsServerSolutions.Setup.ICCommon.StatusInfo
This cmdlet generates either a Boolean value or a **StatusInfo** object.
If you specify the **ValidateOnly** parameter, the cmdlet responds with whether the target server qualifies to run cleanup.
If you do not specify the **ValidateOnly** parameter, the cmdlet provides the service configuration status.

## NOTES

## RELATED LINKS

[Get-WssConfigurationStatus](./Get-WssConfigurationStatus.md)

[Start-WssConfigurationService](./Start-WssConfigurationService.md)

[Test-WssConfigurationOption](./Test-WssConfigurationOption.md)

[Test-WssPrecheckResult](./Test-WssPrecheckResult.md)

