---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Msmq.PowerShell.Commands.dll-Help.xml
Module Name: MSMQ
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/msmq/enable-msmqcertificate?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-MSMQCertificate
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
If you specify the *RenewInternalCertificate* parameter, the cmdlet generates a certificate in your personal certificate store and registers the certificate with Active Directory Domain Services.
The cmdlet returns a **System.Security.Cryptography.X509Certificates.X509Certificate** object that represents the enabled certificate.

## EXAMPLES

### Example 1: Register a certificate
```
PS C:\> $_ | Enable-MsmqCertificate
```

This command registers a certificate stored in the pipeline object variable.
Use this command as part of a script that uses the pipeline.
For more information, type `Get-Help about_Automatic_Variables`.

### Example 2: Create and register a certificate
```
PS C:\> Enable-MsmqCertificate -RenewInternalCertificate
```

This command generates a certificate in your personal certificate store and registers it with Active Directory Domain Services.

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
If you specify the *RenewInternalCertificate* parameter, you cannot specify this parameter.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.Security.Cryptography.X509Certificates.X509Certificate2

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Get-MsmqCertificate](./Get-MSMQCertificate.md)

[Remove-MsmqCertificate](./Remove-MsmqCertificate.md)

