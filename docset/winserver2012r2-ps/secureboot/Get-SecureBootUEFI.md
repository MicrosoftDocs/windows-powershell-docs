---
external help file: Microsoft.SecureBoot.Commands.dll-Help.xml
Module Name: SecureBoot
online version: 
schema: 2.0.0
title: Get-SecureBootUEFI
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 254A50F5-D51F-4432-AAAD-83A14E273B79
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-SecureBootUEFI

## SYNOPSIS
Gets the UEFI variable values related to Secure Boot such as the SetupMode, SecureBoot, KEK, PK, SignatureDatabase, and forbidden SignatureDatabase.

## SYNTAX

```
Get-SecureBootUEFI [-Name] <String> [-OutputFilePath <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SecureBootUEFI** cmdlet gets the UEFI variable values related to Secure Boot which are: SetupMode, SecureBoot, KEK, PK, SignatureDatabase (DB), and forbidden SignatureDatabase (DBX).

If the computer does not support Secure Boot or is a BIOS (non-UEFI) computer, then this cmdlet will return an error displaying the following: `Cmdlet not supported on this platform.`

If the variable does not exist, then this cmdlet will return an error displaying the following: `Variable is currently undefined.`

If Windows PowerShell® is not run in administrator mode, then this cmdlet will return an error displaying the following: `Unable to set proper privileges.
Access was denied.`

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-SecureBootUefi -Name PK | Format-List
Name       : PK 
Bytes      : {161, 89, 192, 165...} 
Attributes : NON VOLATILE 
             BOOTSERVICE ACCESS 
             RUNTIME ACCESS 
             TIME BASED AUTHENTICATED WRITE ACCESS
```

This example gets  information about PK from the UEFI variable.

## PARAMETERS

### -Name
Specifies the name of the UEFI environment variable.

```yaml
Type: String
Parameter Sets: (All)
Aliases: n
Accepted values: PK, KEK, db, dbx, SetupMode, SecureBoot, PKDefault, KEKDefault, dbDefault, dbxDefault, dbt, dbtDefault

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -OutputFilePath
Specifies the output file path of the UEFI environment variable.

```yaml
Type: String
Parameter Sets: (All)
Aliases: f

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String
The String object represents the UEFI variable name.

## OUTPUTS

### Microsoft.SecureBoot.Commands.UEFIEnvironmentVariable
The UEFIEnvironmentVariable object contains the following properties: 

 -- Name 

 -- Bytes 

 -- Attributes

## NOTES

## RELATED LINKS

[Confirm-SecureBootUEFI](./Confirm-SecureBootUEFI.md)

[Format-SecureBootUEFI](./Format-SecureBootUEFI.md)

[Get-SecureBootPolicy](./Get-SecureBootPolicy.md)

[Set-SecureBootUEFI](./Set-SecureBootUEFI.md)

