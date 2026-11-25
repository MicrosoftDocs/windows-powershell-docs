---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.RightsManagementServices.Admin.dll-Help.xml
Module Name: ADRMSADMIN
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adrmsadmin/uninstall-rmsmfgenrollment?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Uninstall-RmsMfgEnrollment
---

# Uninstall-RmsMfgEnrollment

## SYNOPSIS
Terminates the enrollment of an AD RMS server with the Microsoft Federation Gateway.

## SYNTAX

```
Uninstall-RmsMfgEnrollment [-Force] [-GetDefaultCertificate] [-CertificateThumbprint <String>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Uninstall-RmsMfgEnrollment** cmdlet terminates the enrollment of an Active Directory Rights Management Services (AD RMS) server with the Microsoft Federation Gateway.

## EXAMPLES

### Example 1: Terminate enrollment to the Microsoft Federation Gateway with a specified thumbprint
```
PS C:\> Uninstall-RmsMfgEnrollment -CertificateThumbprint "a909502dd82ae41433e6f83886b00d4277a32a7b"
```

This command removes support for Microsoft Federation Gateway from the AD RMS server using the specified certificate thumbprint.

### Example 2: Terminate enrollment with the default certificate
```
PS C:\> Uninstall-RmsMfgEnrollment -GetDefaultCertificate
```

This command removes support for Microsoft Federation Gateway from the AD RMS server by retrieving and using the certificate thumbprint hash for the AD RMS default certificate.

## PARAMETERS

### -CertificateThumbprint
Specifies a string containing the thumbprint hash of the certificate that was used to enroll AD RMS with the Microsoft Federation Gateway.

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
Forces the unenrollment process to be completed, even if there are issues.

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
Indicates that the thumbprint hash of the AD RMS default certificate should be retrieved and used during the removal of support for the AD RMS server to use the Microsoft Federation Gateway.

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

[Install-RmsMfgEnrollment](./Install-RmsMfgEnrollment.md)

