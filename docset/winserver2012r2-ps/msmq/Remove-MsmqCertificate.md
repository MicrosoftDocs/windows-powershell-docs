---
external help file: Microsoft.Msmq.PowerShell.Commands.dll-Help.xml
Module Name: MSMQ
online version: 
schema: 2.0.0
title: Remove-MsmqCertificate
description: 
keywords: powershell, cmdlet
author: kenwith
manager: jasgro
ms.date: 2017-10-30
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 43423EEE-4176-4736-A3B6-874A31BA0D15
ms.author: kenwith
ms.reviewer: brianlic
---

# Remove-MsmqCertificate

## SYNOPSIS
Removes personal certificates.

## SYNTAX

```
Remove-MsmqCertificate -InputObject <X509Certificate2[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-MsmqCertificate** cmdlet removes personal certificates from Active Directory® Domain Services. 
This cmdlet returns the removed Message Queuing (also known as MSMQ) certificate.

## EXAMPLES

### Example 1
```
PS C:\>Get-MsmqCertificate | Remove-MsmqCertificate
```

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

### -InputObject
Specifies an array of certificate objects that represent certificates that this cmdlet removes from Active Directory Domain Services.
This parameter accepts pipeline input.

```yaml
Type: X509Certificate2[]
Parameter Sets: (All)
Aliases: 

Required: True
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

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-MsmqCertificate](./Get-MSMQCertificate.md)

[Enable-MsmqCertificate](./Enable-MSMQCertificate.md)

