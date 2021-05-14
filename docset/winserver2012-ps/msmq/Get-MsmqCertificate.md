---
external help file: MSMQ_Cmdlets.xml
Module Name: MSMQ
online version: https://docs.microsoft.com/powershell/module/msmq/get-msmqcertificate?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
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

