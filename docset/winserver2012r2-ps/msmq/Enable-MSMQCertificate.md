---
external help file: Microsoft.Msmq.PowerShell.Commands.dll-Help.xml
Module Name: MSMQ
online version: 
schema: 2.0.0
title: Enable-MSMQCertificate
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 3A1265A7-FDE8-469E-87B8-9E0EC72E8BBA
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Enable-MsmqCertificate

## SYNOPSIS
Registers a certificate with Active Directory Domain Services.

## SYNTAX

### InputObject
```
Enable-MsmqCertificate -InputObject <X509Certificate2> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### RenewInternalCertificate
```
Enable-MsmqCertificate [-RenewInternalCertificate] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Enable-MsmqCertificate** cmdlet registers a certificate with Active Directory® Domain Services.
If you specify the **RenewInternalCertificate** parameter, the cmdlet generates a certificate in your personal certificate store and  registers the certificate with Active Directory Domain Services. 
The cmdlet returns a **System.Security.Cryptography.X509Certificates.X509Certificate** object that represents the enabled certificate.

## EXAMPLES

### Example 1
```
PS C:\> $_ | Enable-MsmqCertificate
```

### Example 2
```
PS C:\> Enable-MsmqCertificate -RenewInternalCertificate
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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies a certificate object that represents a certificate that this cmdlet registers with Active Directory Domain Services.
If you specify the **RenewInternalCertificate** parameter, you cannot specify this parameter.

```yaml
Type: X509Certificate2
Parameter Sets: InputObject
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -RenewInternalCertificate
Indicates that this cmdlet generates a certificate in the personal certificate store of the user, and registers that certificate with Active Directory Domain Services.
If you pass a certificate to this cmdlet by using the pipeline operator, you cannot specify this parameter.

```yaml
Type: SwitchParameter
Parameter Sets: RenewInternalCertificate
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs. The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
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

[Get-MsmqCertificate](./Get-MSMQCertificate.md)

[Remove-MsmqCertificate](./Remove-MsmqCertificate.md)

