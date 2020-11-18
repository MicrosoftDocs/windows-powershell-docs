---
external help file: Microsoft.RightsManagementServices.Admin.dll-Help.xml
Module Name: ADRMSAdmin
online version: 
schema: 2.0.0
title: Get-RmsCertChain
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: A62ECA60-C9C0-4A12-B621-23A5CEE60F96
---

# Get-RmsCertChain

## SYNOPSIS
Generates a report containing information about the certificate chain of a particular user request for the Active Directory Rights Management Services (AD RMS) cluster.

## SYNTAX

```
Get-RmsCertChain -RequestId <Int64> [-Path] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
This cmdlet generates a report that contains information about the certificate chain of a particular user request on the Active Directory Rights Management Services (AD RMS) cluster.

To obtain the report, specify the RequestID of the user request for which you want a report and then set the Path parameter to the AD RMS provider drive subpath "\<PSDrive\>:\Report" where \<PSDrive\> is the provider drive ID.
You can also specify a relative path.
For example, "." specifies the current location.

Use the Get-RmsUserRequestReport cmdlet to obtain the RequestID of the user request for which you want a certificate chain report.

## EXAMPLES

### --------------  EXAMPLE 1 --------------
```
C:\PS>Get-RmsCertChain -Path . -RequestId 100
```

This command displays the certification chain of the request with the ID of 100.

### --------------  EXAMPLE 2 --------------
```
C:\PS>Get-RmsUserRequestReport -Path . -RequestType GetClientLicensorCertificate -UserId 1 | Get-RmsCertChain -Path .
```

This command uses the Get-RmsUserRequestReport cmdlet to retrieve the ID of a user request and then pipes the ID to the Get-RmsCertChain cmdlet to display the certificate chain of the request.

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

### -Path
Specifies a provider drive and path or relative path on the current drive.
This parameter is required.
Use a dot (.) to specify the current location.
This parameter does not accept wildcards and has no default value.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RequestId
Specifies the unique internal ID of a user request.

```yaml
Type: Int64
Parameter Sets: (All)
Aliases: 

Required: True
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

## OUTPUTS

## NOTES

## RELATED LINKS

[Using Windows PowerShell with AD RMS](https://go.microsoft.com/fwlink/?LinkId=136806)

[Get-RmsCertInfo](./Get-RmsCertInfo.md)

[Get-RmsChildCert](./Get-RmsChildCert.md)

[Get-RmsUserRequestReport](./Get-RmsUserRequestReport.md)

