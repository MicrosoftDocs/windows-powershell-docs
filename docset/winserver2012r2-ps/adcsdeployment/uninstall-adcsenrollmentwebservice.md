---
external help file: Microsoft.CertificateServices.Deployment.Commands.dll-Help.xml
Module Name: ADCSDeployment
online version: 
schema: 2.0.0
title: Uninstall-AdcsEnrollmentWebService
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 9D5ED315-FFAB-406A-BB4C-8D9DF7975B36
---

# Uninstall-AdcsEnrollmentWebService

## SYNOPSIS
Uninstalls the Certificate Enrollment Web service or individual instances of it.

## SYNTAX

### UninstallSingleInstance (Default)
```
Uninstall-AdcsEnrollmentWebService -CAConfig <String> -AuthenticationType <AuthenticationType> [-Force]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### UninstallAll
```
Uninstall-AdcsEnrollmentWebService [-AllEnrollmentServices] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The Uninstall-AdcsEnrollmentWebService cmdlet uninstalls the Certificate Enrollment Web Service either entirely removing all instances of it or partially by removing individual instances.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Uninstall-AdcsEnrollmentWebService -AllEnrollmentServices -force
```

Description

-----------

This command removes all the Web Enrollment role services without prompting for confirmation.

### -------------------------- EXAMPLE 2 --------------------------
```
C:\PS>Uninstall-AdcsEnrollmentWebService -CAConfig APP1.corp.contoso.com\corp-APP1-CA -AuthenticationType Certificate
```

Description

-----------

This command removes the Certificate Enrollment Web Service using the CA specified by the configuration APP1.corp.contoso.com\corp-APP1-CA.
The CA configuration is the CA Computer Name and CA common name separated by a backslash.
The authentication type in use is Certificate.

## PARAMETERS

### -AllEnrollmentServices
Specifies the removal of Certificate Enrollment Web Service instances.

```yaml
Type: SwitchParameter
Parameter Sets: UninstallAll
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AuthenticationType
Specifies the authentication type of the of enrollment services instance to be uninstalled.

```yaml
Type: AuthenticationType
Parameter Sets: UninstallSingleInstance
Aliases: 
Accepted values: Kerberos, UserName, Certificate

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CAConfig
Specifies the configuration string of the certification authority (CA) for which enrollment services will be uninstalled.
This parameter is used to identify which instance of the Certificate Enrollment Web Service is to be uninstalled when multiple are present.

```yaml
Type: String
Parameter Sets: UninstallSingleInstance
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force


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
Shows what would happen if the cmdlet runs. The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### string,enum,bool

## OUTPUTS

### Microsoft.CertificateServices.Deployment.Commands.CES.EnrollmentServiceResult

## NOTES
* The application directories are removed from their respective instance folders in the file system. The uninstall command does not remove the Secure Sockets Layer/Transport Layer Security (SSL/TLS) or the secure hypertext transfer protocol (https) bindings.

  

## RELATED LINKS

[Install-AdcsEnrollmentWebService](./Install-AdcsEnrollmentWebService.md)

