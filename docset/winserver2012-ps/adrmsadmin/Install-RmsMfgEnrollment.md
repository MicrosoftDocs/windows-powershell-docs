---
external help file: Microsoft.RightsManagementServices.Admin.dll-Help.xml
Module Name: ADRMSAdmin
online version: https://learn.microsoft.com/powershell/module/adrmsadmin/install-rmsmfgenrollment?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Install-RmsMfgEnrollment

## SYNOPSIS
Enrolls an AD RMS server with Microsoft Federation Gateway.

## SYNTAX

```
Install-RmsMfgEnrollment [-Force] [-GetDefaultCertificate] [-CertificateThumbprint <String>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The Install-RmsMfgEnrollment cmdlet enrolls an AD RMS server with the Microsoft Federation Gateway.

## EXAMPLES

### --------------  EXAMPLE 1 --------------
```
PS C:\>Install-RmsMfgEnrollment -GetDefaultCertificate
```

Enrolls the AD RMS cluster in the Microsoft Federation Gateway by retrieving and using the thumbprint hash of the AD RMS default certificate.

### --------------  EXAMPLE 2 --------------
```
PS C:\>Install-RmsMfgEnrollment -CertificateThumbprint a909502dd82ae41433e6f83886b00d4277a32a7b
```

Enrolls the AD RMS cluster in the Microsoft Federation Gateway using the thumbprint hash of a non-default certificate.

## PARAMETERS

### -CertificateThumbprint
Specifies a string containing the thumbprint hash of the certificate being used to enroll with the Microsoft Federation Gateway.

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
Forces the process of enrollment to be completed.

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
When specified, indicates that the thumbprint hash of the AD RMS default certificate should be retrieved and used to enroll with the Microsoft Federation Gateway.

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

[Uninstall-RmsMfgEnrollment](./Uninstall-RmsMfgEnrollment.md)

