---
ms.technology: powershell-mdop
ms.mktglfcycl: manage
ms.author: v-anbarr
ms.prod: w10
ms.sitesec: library
author: andreabarr
description: Use this topic to help manage MDOP technologies with Windows PowerShell.
external help file: Microsoft.MBAM.Server.Commands.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro 
ms.assetid: 58405B0D-08C7-4C2F-90AC-BD1F1E0D32B3
ms.date: 12/05/2016
ms.devlang: powershell
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-MbamTPMOwnerPassword
ms.reviewer:
---

# Get-MbamTPMOwnerPassword

## SYNOPSIS
Gets a Trusted Platform Module (TPM).
owner password.

## SYNTAX

```
Get-MbamTPMOwnerPassword -ComputerDomain <String> -ComputerName <String> -Reason <String>
 [-UserDomain <String>] [-UserID <String>] -HelpDeskUrl <Uri> [<CommonParameters>]
```

## DESCRIPTION
The **Get-MbamTPMOwnerPassword** cmdlet gets an owner password for a Trusted Platform Module (TPM).
If a TPM does not accept the user PIN, it becomes locked.
You need to use the owner password to unlock the TPM.

## EXAMPLES

### Example 1: Get the TPM owner password
```
PS C:\> Get-MbamTPMOwnerPassword -ComputerDomain "ContosoDomain" -ComputerName "ContosoComputer" -Reason "Forgot PIN" -HelpDeskUrl https://helpdeskserver/HelpDesk -UserDomain "ContosoDomain" -UserID "ContosoUser"
```

This command gets the TPM owner password from the MBAM help desk server for the specified computer and user.
The command also specifies the reason the TPM is locked.

## PARAMETERS

### -ComputerDomain
Specifies the domain of the locked computer.

```yaml
Type: String
Parameter Sets: (All)
Aliases: cd

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies the name of the locked computer.

```yaml
Type: String
Parameter Sets: (All)
Aliases: cn

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HelpDeskUrl
Specifies the URL for the Microsoft BitLocker Administration and Monitoring (MBAM) help desk site.

```yaml
Type: Uri
Parameter Sets: (All)
Aliases: url

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Reason
Specifies the reason for the password request.

```yaml
Type: String
Parameter Sets: (All)
Aliases: r

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserDomain
Specifies the domain of the user.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ud

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserID
Specifies the ID of the user.

```yaml
Type: String
Parameter Sets: (All)
Aliases: uid

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### String
The TPM owner password.

## NOTES

## RELATED LINKS

[Read-ADTpmInformation](read-adtpminformation.md)

[Write-MbamTPMInformation](write-mbamtpminformation.md)

[Microsoft BitLocker Administration and Monitoring](index.md)


