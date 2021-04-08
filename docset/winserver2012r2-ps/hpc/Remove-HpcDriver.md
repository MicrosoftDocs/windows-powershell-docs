---
author: Kateyanne
description: 
external help file: 
manager: dansimp
Module Name: HPC
ms.author: v-kaunu
ms.date: 12/20/2016
ms.prod: powershell
ms.reviewer: 
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/hpc/remove-hpcdriver?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-HpcDriver
---

# Remove-HpcDriver

## SYNOPSIS
Removes a device driver.

## SYNTAX

### Name (Default)
```
Remove-HpcDriver [-Name] <String[]> [-Scheduler <String[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### Driver
```
Remove-HpcDriver -Driver <HpcDriver[]> [-Scheduler <String[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-HpcDriver** cmdlet removes one or more specified device drivers.
You specify the device drivers by using either **HpcDriver** objects or the names of the setup information (.inf) files for the device drivers.
Do not include the paths for the .inf files.

## EXAMPLES

### Example 1: Remove a device driver
```
PS C:\>Remove-HpcDriver -Name "MyDriver.inf"
```

This command removes the device driver that has a setup information (.inf) file named MyDriver.inf.

### Example 2: Remove drivers in a head node
```
PS C:\>Remove-HpcDriver -Name "Driver01.inf,Driver02.inf" -Scheduler "Headnode"
```

This command removes the device drivers that have setup information (.inf) files named Driver01.inf and Driver02.inf on the HPC cluster with a head node named Headnode.

### Example 3: Get a driver and remove it
```
PS C:\>Get-HpcDriver -Name "MyDriver.inf" | Remove-HpcDriver
```

This command gets the **HpcDriver** object for the device driver that has a setup information file named MyDriver.inf, and then removes that device driver by redirecting that **HpcDriver** object to the **Remove-HpcDriver** cmdlet.

## PARAMETERS

### -Driver
Specifies an array of **HpcDriver** objects for the device drivers that you want to remove.
Use the Get-HpcDriver cmdlet to get the **HpcDriver** objects for the device drivers.

```yaml
Type: HpcDriver[]
Parameter Sets: Driver
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies an array of file names for the setup information (.inf) files for the device drivers that you want to remove.
You do not need to include paths for the .inf files.
Use the Get-HpcDriver cmdlet to view the file names of the .inf files for the device drivers in the HPC cluster.

```yaml
Type: String[]
Parameter Sets: Name
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Scheduler
Specifies the host name or IP address of the head node for the cluster that includes the device drivers.
The value must be a valid computer name or IP address.
If you do not specify the *Scheduler* parameter, this cmdlet uses the scheduler on the head node that the CCP_SCHEDULER environment variable specifies.
To set this environment variable, run the following cmdlet:

`Set-Content Env:CCP_SCHEDULER \<head_node_name\>`

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
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

### HpcDriver[]

## OUTPUTS

### None

## NOTES
* The built-in ConfirmImpact setting for this cmdlet is Medium. If this ConfirmImpact setting is equal to or higher than the value of the $ConfirmPreference variable for your environment, the cmdlet prompts for confirmation unless you specify `-Confirm:$False`. If this ConfirmImpact setting is lower than the value of the $ConfirmPreference variable for your environment, the cmdlet does not prompt for confirmation unless you specify `-Confirm` or `-Confirm:$True`.
* You must be a cluster administrator to run this cmdlet successfully.

## RELATED LINKS

[Add-HpcDriver](./Add-HpcDriver.md)

[Get-HpcDriver](./Get-HpcDriver.md)
