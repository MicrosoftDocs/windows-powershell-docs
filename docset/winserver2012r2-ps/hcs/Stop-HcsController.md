---
external help file: Microsoft.HCS.Management.dll-Help.xml
Module Name: HCS
ms.date: 12/05/2017
online version: https://docs.microsoft.com/powershell/module/hcs/stop-hcscontroller?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-HcsController
---

# Stop-HcsController

## SYNOPSIS
Stops a controller.

## SYNTAX

```
Stop-HcsController [-ControllerId <ControllerIds>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Stop-HcsController** cmdlet stops a controller.
If you run the cmdlet without any parameters, it stops the current controller.
The current controller is the controller where you run the cmdlet.

You can use the **ControllerID** parameter to specify a different controller to stop.

## EXAMPLES

### Example 1: Stop a controller
```
PS C:\> Stop-HcsController -ControllerId Controller1
Checking device state...

This command will shut down your standby controller.  To power up the 
controller again, you will need to push the power button on the controller. 
Are you sure you want to continue with this operation?
[Y] Yes  [N] No  [?] Help (default is "Y"): y
```

This command stops the controller specified by the **ControllerID** parameter.

### Example 2: Restart a controller
```
PS C:\> Stop-HcsController

Checking device state...

This command will shut down your standby controller. To power up the 
controller again, you will need to push the power button on the controller. 
Are you sure you want to continue with this operation?
[Y] Yes  [N] No  [?] Help (default is "Y"): y
```

This command restarts the current controller.
In this example, the command restarts the standby controller.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Restart-HcsController](./Restart-HcsController.md)

