---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.UpdateServices.Commands.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Invoke-WsusServerCleanup
ms.reviewer:
ms.assetid: 807AAA72-2378-4F8A-9595-5FC2825E7699
---

# Invoke-WsusServerCleanup

## SYNOPSIS
Performs the process of cleanup on a WSUS server.

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

### Example 1: Run cleanup for obsolete computers
```
PS C:\> Get-WsusServer | Invoke-WsusServerCleanup -CleanupObsoleteComputers
Obsolete Computers Deleted: 1
```

This command runs this cmdlet on the local WSUS server specifying the option to clean up obsolete computers.

### Example 2: Run cleanup for obsolete computers and updates
```
PS C:\> Get-WsusServer "contoso" | Invoke-WsusServerCleanup -CleanupObsoleteComputers -CleanupObsoleteUpdates
Obsolete Updates Deleted: 62 
Obsolete Computers Deleted: 0
```

This command runs this cmdlet on the server named contoso specifying the options to clean up obsolete computers and obsolete updates.

## PARAMETERS

### -CleanupObsoleteComputers
Specifies that the cmdlet deletes obsolete computers from the database.

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
Specifies that the cmdlet deletes obsolete updates from the database.

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
Specifies that the cmdlet deletes unneeded update files.

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
Specifies that the cmdlet deletes obsolete revisions to updates from the database.

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
Specifies that the cmdlet declines expired updates.

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
Specifies that the cmdlet declines superseded updates.

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
This value is obtained by calling the [Get-WsusServer](./Get-WsusServer.md) cmdlet and passing the resulting **IUpdateServer** object into this cmdlet.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.UpdateServices.Commands.IUpdateServer

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Get-WsusServer](./Get-WsusServer.md)

