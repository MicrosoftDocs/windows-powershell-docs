---
external help file: wsbcmdlet.dll-Help.xml
Module Name: WindowsServerBackup
online version: 
schema: 2.0.0
title: Add-WBVirtualMachine
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 4F9AFA05-30C3-481C-9820-023C325F4C0D
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Add-WBVirtualMachine

## SYNOPSIS
Adds a list of virtual machines to the backup policy.

## SYNTAX

### WBVirtualMachine
```
Add-WBVirtualMachine [-Policy] <WBPolicy> [[-VirtualMachine] <WBVirtualMachine[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### All
```
Add-WBVirtualMachine [-Policy] <WBPolicy> [-All] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-WBVirtualMachine** cmdlet adds a list of virtual machines to a backup policy contained in the specified **WBPolicy** object.

## EXAMPLES

### Example 1: Add virtual machines to the backup policy
```
PS C:\> $Policy = Get-WBPolicy
PS C:\> $VirtualMachines = Get-WBVirtualMachine
PS C:\> Add-WBVirtualMachine -Policy $Policy -VirtualMachine $VirtualMachines
```

This example adds the list of volumes in the **$VirtualMachines** variable to the **WBPolicy** object **$Policy**.

The first command stores the result of the Get-WBPolicy cmdlet in the **$Policy** variable.

The second command stores the result of the **Get-WBVirtualMachine** cmdlet in the **$VirtualMachines** variable.

The third command adds the virtual machines listed in the **$VirtualMachines** variable to the backup policy in the **$Policy** variable.

## PARAMETERS

### -All
Indicates that all virtual machines on the computer are added to the policy.

```yaml
Type: SwitchParameter
Parameter Sets: All
Aliases: 

Required: False
Position: 1
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

### -Policy
Specifies a **WBPolicy** object that contains the backup policy to update.

```yaml
Type: WBPolicy
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualMachine
Specifies an array of one or more virtual machines to add to the **WBPolicy** object.

```yaml
Type: WBVirtualMachine[]
Parameter Sets: WBVirtualMachine
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
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

[Get-WBVirtualMachine](./Get-WBVirtualMachine.md)

[Remove-WBVirtualMachine](./Remove-WBVirtualMachine.md)

