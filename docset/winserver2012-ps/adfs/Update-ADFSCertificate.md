---
external help file: Microsoft.IdentityServer.PowerShell.dll-Help.xml
Module Name: ADFS
online version: https://docs.microsoft.com/powershell/module/adfs/update-adfscertificate?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Update-ADFSCertificate

## SYNOPSIS
Updates the certificates of the Federation Service.

## SYNTAX

```
Update-ADFSCertificate [[-CertificateType] <String>] [-Urgent] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The Update-ADFSCertificate cmdlet creates new certificates for the Federation Service.
When automatic certificate rollover is enabled and Active Directory Federation Services (AD FS) 2.0 is managing the certificates that are used for signing, this update cmdlet can be used to initiate a rollover.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Update-ADFSCertificate -CertificateType Token-Signing
```

Description

-----------

Updates the token-signing certificate.

## PARAMETERS

### -CertificateType
Indicates the type of certificate to rollover. 
Valid types include Token-Encryption and Token-Signing.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Accepted values: Token-Decrypting, Token-Signing

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -PassThru
```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Urgent
Specifies that the certificate rollover should happen immediately.
An urgent rollover removes older certificates immediately.
It might result in a service outage as trusts update to use the new certificates.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

### None

## OUTPUTS

### None

## NOTES
* The Urgent parameter option is useful for emergency rollover situations in which a key might be compromised.

## RELATED LINKS

[Add-ADFSCertificate](./Add-ADFSCertificate.md)

[Remove-ADFSCertificate](./Remove-ADFSCertificate.md)

