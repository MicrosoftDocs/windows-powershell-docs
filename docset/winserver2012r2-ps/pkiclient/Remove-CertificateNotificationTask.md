---
external help file: Microsoft.CertificateServices.PKIClient.Cmdlets.dll-Help.xml
Module Name: PKI
online version: 
schema: 2.0.0
title: Remove-CertificateNotificationTask
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 3E0D9B0B-766A-4EF6-B4C7-1CF6D1FF0FF5
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Remove-CertificateNotificationTask

## SYNOPSIS
Removes a certificate notification task from Task Scheduler.

## SYNTAX

```
Remove-CertificateNotificationTask [-Name] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-CertificateNotificationTask** cmdlet removes from Task Scheduler a certificate notification task that was registered with the New-CertificateNotificationTask cmdlet.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Remove-CertificateNotificationTask -Name "My Task"
```

This example removes the task named My Task.

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

### -Name
Identifies the notification task to be deleted.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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

### System.String
A String containing the name of the task to be removed.

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Get-CertificateNotificationTask](./Get-CertificateNotificationTask.md)

[New-CertificateNotificationTask](./New-CertificateNotificationTask.md)

[Switch-Certificate](./Switch-Certificate.md)

