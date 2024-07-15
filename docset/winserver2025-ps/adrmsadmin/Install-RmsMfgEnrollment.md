---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.RightsManagementServices.Admin.dll-Help.xml
Module Name: ADRMSADMIN
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adrmsadmin/install-rmsmfgenrollment?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Install-RmsMfgEnrollment
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
The **Install-RmsMfgEnrollment** cmdlet enrolls an Active Directory Rights Management Services (AD RMS) server with the Microsoft Federation Gateway.

## EXAMPLES

### Example 1: Enroll in the Microsoft Federation Gateway using the default certificate
```
PS C:\> Install-RmsMfgEnrollment -GetDefaultCertificate
```

This command enrolls the AD RMS cluster in the Microsoft Federation Gateway by retrieving and using the thumbprint hash of the AD RMS default certificate.

### Example 2: Enroll in the Microsoft Federation Gateway using a specified certificate
```
PS C:\> Install-RmsMfgEnrollment -CertificateThumbprint "a909502dd82ae41433e6f83886b00d4277a32a7b"
```

This command enrolls the AD RMS cluster in the Microsoft Federation Gateway using the thumbprint hash of a non-default certificate.

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
Indicates that the thumbprint hash of the AD RMS default certificate should be retrieved and used to enroll with the Microsoft Federation Gateway.

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

[Uninstall-RmsMfgEnrollment](./Uninstall-RmsMfgEnrollment.md)

