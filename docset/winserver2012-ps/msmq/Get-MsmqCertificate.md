---
external help file: MSMQ_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: 02BEFEEE-443C-4A15-AA58-4497B9C344A2
manager: dansimp
---

# Get-MsmqCertificate

## SYNOPSIS
Gets an array of object type System.Security.Cryptography.X509Certificates.X509Certificate.

## SYNTAX

```
Get-MsmqCertificate [[-ComputerName] <String>]
```

## DESCRIPTION
The **Get-MsmqCertificate** cmdlet returns an array of object type **System.Security.Cryptography.X509Certificates.X509Certificate**.
Each entry represents a personal certificate that is currently registered in Active Directory Domain Services.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -ComputerName
Specifies the certificates of the current user for the specified host or virtual server.
If you do not specify this parameter the cmdlet gets the certificates of the current user for all hosts or virtual servers.

```yaml
Type: String
Parameter Sets: (All)
Aliases: cn

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Enable-MsmqCertificate](./Enable-MsmqCertificate.md)

[Remove-MsmqCertificate](./Remove-MsmqCertificate.md)

