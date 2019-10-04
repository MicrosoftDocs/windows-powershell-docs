---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.CertificateServices.Administration.Commands.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/27/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Restore-CARoleService
ms.reviewer:
ms.assetid: 6AB4E278-DA57-44BD-AC5E-6E0BECE6A574
---

# Restore-CARoleService

## SYNOPSIS
Restores the CA database and private key information.

## SYNTAX

### Key
```
Restore-CARoleService [-Path] <String> [-Force] [-KeyOnly] [-Password <SecureString>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Database
```
Restore-CARoleService [-Path] <String> [-Force] [-DatabaseOnly] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### All
```
Restore-CARoleService [-Path] <String> [-Force] [-Password <SecureString>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Restore-CARoleService** cmdlet restores the certification authority (CA) database and private key information.

## EXAMPLES

### Example 1: Restore the CA private key and certificate
```
PS C:\> Restore-CARoleService -Path "C:\CABackup"
```

This command restores the CA private key and certificate from the specified path.

### Example 2: Restore the CA database only
```
PS C:\> Restore-CARoleService -Path "C:\CABackup" -DatabaseOnly
```

This command restores the CA database from the specified path.
The command does not restore the CA private key information.

### Example 3: Restore the CA key only
```
PS C:\> Restore-CARoleService -Path "C:\CABackup" -KeyOnly
```

This command restores the CA private key information to the specified path.
The command does not restore the CA database.

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

### -DatabaseOnly
Indicates that the cmdlet restores only the certification authority database.

```yaml
Type: SwitchParameter
Parameter Sets: Database
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -KeyOnly
Indicates that the cmdlet restores only the certification authority private key and certificate.

```yaml
Type: SwitchParameter
Parameter Sets: Key
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Password
Specifies a password, as a secure string, to access the private key and certificate information.
To obtain a secure string, use the [ConvertTo-SecureString](http://go.microsoft.com/fwlink/?LinkID=113291) cmdlet.
For more information, type `Get-Help ConvertTo-SecureString`.

```yaml
Type: SecureString
Parameter Sets: Key, All
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path
Specifies the directory from which the cmdlet restores the CA database and private key.
The cmdlet restores the database from the subdirectory named Database in the path that you specified when you backed up the CA database.
The cmdlet restores the private key from the .p12 file that you backed up in the Database subdirectory in the path that you specify.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Backup-CARoleService](./Backup-CARoleService.md)

