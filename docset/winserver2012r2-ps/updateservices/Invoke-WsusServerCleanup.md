---
external help file: Microsoft.UpdateServices.Commands.dll-Help.xml
Module Name: UpdateServices
online version: 
schema: 2.0.0
title: Invoke-WsusServerCleanup
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 807AAA72-2378-4F8A-9595-5FC2825E7699
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Invoke-WsusServerCleanup

## SYNOPSIS
Performs the process of cleanup on a specified Windows Server Update Services (WSUS) server.

## SYNTAX

```
Invoke-WsusServerCleanup [-UpdateServer <IUpdateServer>] [-CleanupObsoleteComputers] [-CleanupObsoleteUpdates]
 [-CleanupUnneededContentFiles] [-CompressUpdates] [-DeclineExpiredUpdates] [-DeclineSupersededUpdates]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Invoke-WsusServerCleanup** cmdlet performs the process of cleanup on a specified Windows Server Update Services (WSUS) server.
This process has the same impact as running the **Cleanup Wizard** from within the WSUS Console application and allows the specification of the same options as parameters.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Get-WsusServer | Invoke-WsusServerCleanup -CleanupObsoleteComputers
Obsolete Computers Deleted: 1
```

This example runs this cmdlet on the local WSUS Server specifying the option to clean up obsolete computers.

### EXAMPLE 2
```
PS C:\> Get-WsusServer contoso | Invoke-WsusServerCleanup -CleanupObsoleteComputers -CleanupObsoleteUpdates
Obsolete Updates Deleted: 62 
Obsolete Computers Deleted: 0
```

This example runs this cmdlet on the server named contoso specifying the options to clean up obsolete computers and obsolete updates.

## PARAMETERS

### -CleanupObsoleteComputers
Specifies that obsolete computers should be deleted from the database.

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

### -CleanupObsoleteUpdates
Specifies that obsolete updates should be deleted from the database.

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

### -CleanupUnneededContentFiles
Specifies that unneeded update files should be deleted.

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

### -CompressUpdates
Specifies that obsolete revisions to updates should be deleted from the database.

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

### -DeclineExpiredUpdates
Specifies that expired updates should be declined.

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

### -DeclineSupersededUpdates
Specifies that superseded updates should be declined.

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

### -UpdateServer
Specifies the object that contains the WSUS server.
This value is obtained by calling the Get-WsusServer cmdlet and piping the resulting IUpdateServer object into this cmdlet.

```yaml
Type: IUpdateServer
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
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

### Microsoft.UpdateServices.Commands.IUpdateServer
IUpdateServer

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Get-WsusServer](./Get-WsusServer.md)

