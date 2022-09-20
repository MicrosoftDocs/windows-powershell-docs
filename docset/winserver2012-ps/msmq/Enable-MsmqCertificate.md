---
external help file: MSMQ_Cmdlets.xml
Module Name: MSMQ
online version: https://learn.microsoft.com/powershell/module/msmq/enable-msmqcertificate?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Enable-MsmqCertificate

## SYNOPSIS
Registers a certificate with Active Directory Domain Services.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Enable-MsmqCertificate -InputObject <X509Certificate2> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Enable-MsmqCertificate [-RenewInternalCertificate] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Enable-MsmqCertificate** cmdlet registers a certificate with Active Directory Domain Services.
If the **RenewInternalCertificate** parameter is specified, the cmdlet generates a new certificate in the user's personal certificate store and registers it with Active Directory Domain Services.
It returns a **System.Security.Cryptography.X509Certificates.X509Certificate** object that represents the enabled certificate.

## EXAMPLES

### Example 1: Register a certificate with Active Directory Domain Services
```
PS C:\>$_ | Enable-MsmqCertificate
PS C:\> RenewInternalCertificate
```

This first command registers a certificate with Active Directory Domain Services.
The final command renews the certificate.

## PARAMETERS

### -InputObject
Specifies a certificate object that represents a certificate that is registered with the Active Directory Domain Services.
This parameter cannot be used if the **RenewInternalCertificate** parameter is specified.

```yaml
Type: X509Certificate2
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True(ByValue)
Accept wildcard characters: False
```

### -RenewInternalCertificate
Indicates that this cmdlet generates a new certificate in the user's personal certificate store and registers it with Active Directory Domain Services.
This parameter cannot be used if the **X509Certificate2** parameter is specified or if a certificate is piped to this cmdlet's input.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
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
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-MsmqCertificate](./Get-MsmqCertificate.md)

[Remove-MsmqCertificate](./Remove-MsmqCertificate.md)

