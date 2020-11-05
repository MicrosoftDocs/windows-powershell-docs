---
external help file:
Module Name: hpc
online version:
schema: 2.0.0
title: Remove-HpcJobCredential
description:
keywords: powershell, cmdlet
ms.date: 12/20/2016
ms.prod: powershell
ms.technology: powershell
ms.topic: reference
online version: http://go.microsoft.com/fwlink/?LinkId=182659
schema: 2.0.0
ms.assetid: B0D29FB7-E5E3-466A-8247-05A7151F1734
manager: dansimp
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Remove-HpcJobCredential

## SYNOPSIS
Deletes cached credentials that the job scheduler uses to submit jobs.

## SYNTAX

```
Remove-HpcJobCredential [[-UserName] <String[]>] [-Scheduler <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-HpcJobCredential** cmdlet deletes the cached credentials for one or more specified users that the job scheduler uses to submit jobs.
If you do not specify a user name, the cmdlet deletes the credential of the user who ran the cmdlet.

## EXAMPLES

### Example 1: Remove credentials for a user
```
PS C:\>Remove-HpcJobCredential -UserName "CONTOSO\pfuller"
```

This command deletes the credentials for the user with a user name of pfuller and a domain of CONTOSO from the cached credentials that the job scheduler uses to submit jobs.

## PARAMETERS

### -Scheduler
Specifies the host name or IP address of the head node for the cluster for which the specified user can submit jobs.
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

### -UserName
Specifies an array of names of  users for whom you want to delete cached credentials.

```yaml
Type: String[]
Parameter Sets: (All)
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

### None

## OUTPUTS

### None

## NOTES
* You cannot delete installation credentials, but can only delete credentials that the job scheduler users to submit jobs.
* The built-in ConfirmImpact setting for this cmdlet is Medium. If this ConfirmImpact setting is equal to or higher than the value of the $ConfirmPreference variable for your environment, the cmdlet prompts for confirmation unless you specify `-Confirm:$False`. If this ConfirmImpact setting is lower than the value of the $ConfirmPreference variable for your environment, the cmdlet does not prompt for confirmation unless you specify `-Confirm` or `-Confirm:$True`.

## RELATED LINKS

[Get-HpcJobCredential](./Get-HpcJobCredential.md)

[Set-HpcJobCredential](./Set-HpcJobCredential.md)
