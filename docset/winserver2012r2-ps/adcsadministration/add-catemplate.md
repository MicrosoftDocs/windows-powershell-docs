---
external help file: Microsoft.CertificateServices.Administration.Commands.dll-Help.xml
Module Name: ADCSAdministration
online version: 
schema: 2.0.0
title: Add-CATemplate
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: C8A5382D-23F3-4DDE-9661-EAF69E65B2AB
---

# Add-CATemplate

## SYNOPSIS
Adds a certificate template to the CA.

## SYNTAX

```
Add-CATemplate [-Name] <String> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The Add-CATemplate cmdlet adds a certificate template to the CA for issuing.

A certificate template is a preconfigured list of certificate settings that allows users and computers to enroll for certificates without having to create complex certificate requests.
Certificate templates allow for the customization of a certificate that can be issued by the CA.
The template defines items such as the cryptographic types, validity and renewal periods, and certificate purposes.

The certificate templates are stored in Active Directory Domain Services (AD DS).
Many default certificate templates are added to AD DS when the CA role service is installed.
The Add-CATemplate cmdlet does not allow you to create new templates or duplicate existing templates.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Add-CATemplate -Name EFS
```

Description

-----------

Adds a CA template with the template display name Basic EFS and the template name EFS.

## PARAMETERS

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
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of a certificate template name.
This name must always be the template name (short name without spaces) and not the template display name.
For example, the certificate template with the template display name of Exchange Enrollment Agent (Offline request) must be specified by its template name, which is EnrollmentAgentOffline.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
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

### System.String
There is only one parameter for this cmdlet (Name) and it can only accept a single template each time specified by name as a string.

## OUTPUTS

### None

## NOTES
* To perform this procedure, you must be a member of the Domain Admins group or the Enterprise Admins group in Active Directory Domain Services (AD DS), or you must have been delegated the appropriate authority. As a security best practice, consider using Run as to perform this procedure.

## RELATED LINKS

[Get-CATemplate](./Get-CATemplate.md)

[Remove-CATemplate](./Remove-CATemplate.md)

