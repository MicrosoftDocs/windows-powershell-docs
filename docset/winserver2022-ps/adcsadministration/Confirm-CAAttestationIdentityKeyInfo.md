---
external help file: Microsoft.CertificateServices.Administration.Commands.dll-Help.xml
Module Name: ADCSAdministration
online version:
schema: 2.0.0
---

# Confirm-CAAttestationIdentityKeyInfo

## SYNOPSIS
{{ Fill in the Synopsis }}

## SYNTAX

### PublicKeyHash
```
Confirm-CAAttestationIdentityKeyInfo [-PublicKeyHash] <String> [<CommonParameters>]
```

### Certificate
```
Confirm-CAAttestationIdentityKeyInfo [-Certificate] <X509Certificate2> [<CommonParameters>]
```

## DESCRIPTION
{{ Fill in the Description }}

## EXAMPLES

### Example 1
```powershell
PS C:\> {{ Add example code here }}
```

{{ Add example description here }}

## PARAMETERS

### -Certificate
{{ Fill Certificate Description }}

```yaml
Type: X509Certificate2
Parameter Sets: Certificate
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -PublicKeyHash
{{ Fill PublicKeyHash Description }}

```yaml
Type: String
Parameter Sets: PublicKeyHash
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.Security.Cryptography.X509Certificates.X509Certificate2

## OUTPUTS

### System.Boolean

## NOTES

## RELATED LINKS
