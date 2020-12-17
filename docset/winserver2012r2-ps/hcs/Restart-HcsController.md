---
external help file: Microsoft.HCS.Management.dll-Help.xml
online version: 
schema: 2.0.0
title: Restart-HcsController
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 634CE6BB-B9E6-4B1F-B358-C07698E8AA5F
---

# Restart-HcsController

## SYNOPSIS
Restarts a controller.

## SYNTAX

```
Restart-HcsController [-ControllerId <ControllerIds>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Restart-HcsController** cmdlet restarts a controller.
If you run the cmdlet without any parameters, it restarts the current controller.
The current controller is the controller where you run the cmdlet.
You can use the **ControllerID** parameter to specify a different controller to restart.

## EXAMPLES

### Example 1: Restart a controller
```
PS C:\> Restart-HcsController -ControllerId 0
Checking device state...

This command will restart your standby controller.
Are you sure you want to continue with this operation?
[Y] Yes  [N] No  [?] Help (default is "Y"): y
```

This command restarts the controller specified by the **ControllerID** parameter.
In this example, controller0 is the standby controller.

### Example 2: Restart the current controller
```
PS C:\> Restart-HcsController

Checking device state...

This command will restart your active controller. Restarting the active controller will cause a failover to the standby
controller.
Are you sure you want to continue with this operation?
[Y] Yes  [N] No  [?] Help (default is "Y"): n
```

This command restarts the current controller.
In this example, the controller is the active controller.
The current controller does not have to be the active controller.

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

### -ControllerId
Specifies controller0 or controller1.

```yaml
Type: ControllerIds
Parameter Sets: (All)
Aliases: 
Accepted values: Controller0, Controller1

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

[Stop-HcsController](./Stop-HcsController.md)

