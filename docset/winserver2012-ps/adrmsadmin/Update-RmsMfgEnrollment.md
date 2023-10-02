---
external help file: Microsoft.RightsManagementServices.Admin.dll-Help.xml
Module Name: ADRMSAdmin
online version: https://learn.microsoft.com/powershell/module/adrmsadmin/update-rmsmfgenrollment?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Update-RmsMfgEnrollment

## SYNOPSIS
Updates enrollment information for an AD RMS server enrolled with the Microsoft Federation Gateway service.

## SYNTAX

```
Update-RmsMfgEnrollment [-TokenCert] [-SigningCert] [-SetCertificatePermissions] [-Force]
 [-GetDefaultCertificate] [-CertificateThumbprint <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The Update-RmsMfgEnrollment cmdlet updates enrollment information for an AD RMS server enrolled with the Microsoft Federation Gateway service.

## EXAMPLES

### --------------  EXAMPLE 1 --------------
```
PS C:\>Update-RmsMfgEnrollment -GetDefaultCertificate
```

Updates the Microsoft Federation Gateway support enrollment for the current AD RMS server by retrieving and using the thumbprint hash of the AD RMS default certificate.

### --------------  EXAMPLE 2 --------------
```
PS C:\>Update-RmsMfgEnrollment -CertificateThumbprint a909502dd82ae41433e6f83886b00d4277a32a7b
```

Updates the Microsoft Federation Gateway support enrollment for the current AD RMS server using the thumbprint hash of a non-default certificate.

### --------------  EXAMPLE 3 --------------
```
PS C:\>Update-RmsMfgEnrollment -SigningCert
```

Updates the Microsoft Federation Gateway support enrollment for the current AD RMS server using the thumbprint hash of a non-default certificate.

### --------------  EXAMPLE 4 --------------
```
PS C:\>Update-RmsMfgEnrollment -TokenCert
```

Updates the Microsoft Federation Gateway support enrollment for the current AD RMS server using the thumbprint hash of a non-default certificate.

### --------------  EXAMPLE 5 --------------
```
PS C:\>Update-RmsMfgEnrollment -SetCertificatePermissions
```

Sets certificate permissions for the Microsoft Federation Gateway support enrollment for the current AD RMS.

## PARAMETERS

### -CertificateThumbprint
Specifies a string containing the thumbprint hash of the certificate being used to update enrollment with the Microsoft Federation Gateway.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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

### -Force
Forces the process of updating the enrollment to be completed.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -GetDefaultCertificate
When specified, indicates that the thumbprint hash of the AD RMS default certificate should be retrieved and used to update enrollment with the Microsoft Federation Gateway.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -SetCertificatePermissions
When specified, indicates that permissions are to be set on the AD RMS server enrollment with the Microsoft Federation Gateway.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -SigningCert
When specified, indicates that the Microsoft Federation Gateway signing certificate should be updated (or refreshed in metadata) for the current AD RMS server enrollment.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -TokenCert
When specified, indicates that the token decryption certificate should be updated for the AD RMS server enrollment with the Microsoft Federation Gateway.

You can update the token decryption certificate or the Microsoft Federation Gateway certificate, as needed.
Because the token decryption certificate is the SSL certificate for the AD RMS cluster, you must update the token decryption certificate if the cluster SSL certificate expires.
After you update the token decryption certificate, you must grant the AD RMS Services group permission to access the certificate on all servers in the AD RMS cluster.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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

## RELATED LINKS

