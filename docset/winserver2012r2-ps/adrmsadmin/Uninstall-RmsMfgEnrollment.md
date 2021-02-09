---
external help file: Microsoft.RightsManagementServices.Admin.dll-Help.xml
Module Name: ADRMSAdmin
online version: 
schema: 2.0.0
title: Uninstall-RmsMfgEnrollment
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 5106BC37-49FA-4B6C-AF55-633BCB38B546
---

# Uninstall-RmsMfgEnrollment

## SYNOPSIS
Terminates the enrollment of an rms_2 server with the Microsoft Federation Gateway.

## SYNTAX

```
Uninstall-RmsMfgEnrollment [-Force] [-GetDefaultCertificate] [-CertificateThumbprint <String>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The Uninstall-RmsMfgEnrollment cmdlet terminates the enrollment of an rms_2 server with the Microsoft Federation Gateway.

## EXAMPLES

### --------------  EXAMPLE 1 --------------
```
PS C:\>Uninstall-RmsMfgEnrollment -CertificateThumbprint a909502dd82ae41433e6f83886b00d4277a32a7b
```

Removes support for Microsoft Federation Gateway form the AD RMS server using the specified certificate thumbprint.

### --------------  EXAMPLE 2 --------------
```
PS C:\>Uninstall-RmsMfgEnrollment -GetDefaultCertificate
```

Removes support for Microsoft Federation Gateway from the AD RMS server by retrieving and using the certificate thumbprint hash for the AD RMS default certificate.

## PARAMETERS

### -CertificateThumbprint
Specifies a string containing the thumbprint hash of the certificate that was used to enroll rms_2 with the Microsoft Federation Gateway.

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
When specified, indicates that the thumbprint hash of the AD RMS default certificate should be retrieved and used during the removal of support for the AD RMS server to use the Microsoft Federation Gateway.

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

[Using Windows PowerShell with AD RMS](https://go.microsoft.com/fwlink/?LinkId=136806)

[Install-RmsMfgEnrollment](./Install-RmsMfgEnrollment.md)

