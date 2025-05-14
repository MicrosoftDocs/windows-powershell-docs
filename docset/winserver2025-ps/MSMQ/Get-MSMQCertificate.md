---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Msmq.PowerShell.Commands.dll-Help.xml
Module Name: MSMQ
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/msmq/get-msmqcertificate?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-MSMQCertificate
---

# Get-MsmqCertificate

## SYNOPSIS
Gets certificates registered in Active Directory Domain Services.

## SYNTAX

```
Get-MsmqCertificate [[-ComputerName] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-MsmqCertificate** cmdlet gets an array of **System.Security.Cryptography.X509Certificates.X509Certificate** objects.
Each object represents a personal certificate that is currently registered in Active Directory® Domain Services.

## EXAMPLES

### Example 1: Get all certificates of the current user
```
PS C:\> Get-MsmqCertificate
```

This command gets the certificates of the current user for all hosts or virtual servers.

### Example 2: Get the certificates of the current user for a host or virtual server
```
PS C:\> Get-MsmqCertificate -ComputerName "Contoso27"
```

This command gets the certificates of the current user for the host or virtual server named Contoso27.

## PARAMETERS

### -ComputerName
Specifies the name of a host or virtual server.
This cmdlet gets the certificates of the current user for the specified host or virtual server.
If you do not specify this parameter, this cmdlet gets the certificates of the current user for all hosts or virtual servers.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Enable-MsmqCertificate](./Enable-MSMQCertificate.md)

[Remove-MsmqCertificate](./Remove-MsmqCertificate.md)

