---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.RightsManagementServices.Admin.dll-Help.xml
Module Name: ADRMSADMIN
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adrmsadmin/update-rmsmfgenrollment?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Update-RmsMfgEnrollment
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
The **Update-RmsMfgEnrollment** cmdlet updates enrollment information for an Active Directory Rights Management Services (AD RMS) server enrolled with the Microsoft Federation Gateway service.

## EXAMPLES

### Example 1: Update support enrollment using the default certificate
```
PS C:\> Update-RmsMfgEnrollment -GetDefaultCertificate
```

This command updates the Microsoft Federation Gateway support enrollment for the current AD RMS server by retrieving and using the thumbprint hash of the AD RMS default certificate.

### Example 2: Update support enrollment using a specified certificate
```
PS C:\> Update-RmsMfgEnrollment -CertificateThumbprint "a909502dd82ae41433e6f83886b00d4277a32a7b"
```

This command updates the Microsoft Federation Gateway support enrollment for the current AD RMS server using the thumbprint hash of a non-default certificate.

### Example 3: Update the signing certificate for the enrollment
```
PS C:\> Update-RmsMfgEnrollment -SigningCert
```

This command updates the Microsoft Federation Gateway support enrollment for the current AD RMS server.

### Example 4: Update the token decryption certificate
```
PS C:\> Update-RmsMfgEnrollment -TokenCert
```

This command updates the token decryption certificate for the current AD RMS server.

### Example 5: Set certificate permissions for the Microsoft Federation Gateway
```
PS C:\> Update-RmsMfgEnrollment -SetCertificatePermissions
```

This command sets certificate permissions for the Microsoft Federation Gateway support enrollment for the current AD RMS.

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
Forces the command to run without asking for user confirmation.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Using Windows PowerShell with AD RMS](https://go.microsoft.com/fwlink/?LinkId=136806)

