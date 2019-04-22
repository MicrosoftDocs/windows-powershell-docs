---
external help file: Microsoft.Msmq.PowerShell.Commands.dll-Help.xml
Module Name: MSMQ
online version: 
schema: 2.0.0
title: Get-MSMQCertificate
description: 
keywords: powershell, cmdlet
author: kenwith
manager: jasgro
ms.date: 2017-10-30
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 02BEFEEE-443C-4A15-AA58-4497B9C344A2
ms.author: kenwith
ms.reviewer: brianlic
---

# Get-MsmqCertificate

## SYNOPSIS
Returns certificates registered in Active Directory Domain Services.

## SYNTAX

```
Get-MsmqCertificate [[-ComputerName] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-MsmqCertificate** cmdlet returns an array of **System.Security.Cryptography.X509Certificates.X509Certificate** objects.
Each object represents a personal certificate that is currently registered in Active Directory® Domain Services.

## EXAMPLES

### Example 1
```
PS C:\>Get-MsmqCertificate
```

### Example 2
```
PS C:\>Get-MsmqCertificate -ComputerName "Contoso27"
```

## PARAMETERS

### -ComputerName
Specifies a host or virtual server.
This cmdlet gets the certificates of the current user for the specified host or virtual server.
If you do not specify this parameter, this cmdlet gets the certificates of the current user for all hosts or virtual servers.
The default value is an empty string.

```yaml
Type: String
Parameter Sets: (All)
Aliases: cn

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Enable-MsmqCertificate](./Enable-MSMQCertificate.md)

[Remove-MsmqCertificate](./Remove-MsmqCertificate.md)

