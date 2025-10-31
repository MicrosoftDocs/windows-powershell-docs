---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.CertificateServices.Administration.Commands.dll-Help.xml
Module Name: ADCSAdministration
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/adcsadministration/backup-caroleservice?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Backup-CARoleService
---

# Backup-CARoleService

## SYNOPSIS
Backs up the CA database and private key information.

## SYNTAX

### Key
```
Backup-CARoleService [-Path] <String> [-Force] [-KeyOnly] [-Password <SecureString>] [<CommonParameters>]
```

### Database
```
Backup-CARoleService [-Path] <String> [-Force] [-DatabaseOnly] [-Incremental] [-KeepLog] [<CommonParameters>]
```

### All
```
Backup-CARoleService [-Path] <String> [-Force] [-Password <SecureString>] [-Incremental] [-KeepLog]
 [<CommonParameters>]
```

## DESCRIPTION
The **Backup-CARoleService** cmdlet backs up the certification authority (CA) database and private key information to a specified path.

## EXAMPLES

### Example 1: Back up the CA database and private key information
```
PS C:\> Backup-CARoleService -Path "C:\CABackup"
```

This command exports the CA database and private key information to the specified path.

### Example 2: Back up the CA database only
```
PS C:\> Backup-CARoleService -Path "C:\CABackup" -DatabaseOnly
```

This command exports the CA database to the specified path.
The command does not back up the CA private key information.

### Example 3: Back up the CA key only
```
PS C:\> Backup-CARoleService -Path "C:\CABackup" -KeyOnly
```

This command exports the CA private key information to the specified path.
The command does not back up the CA database.

## PARAMETERS

### -DatabaseOnly
Indicates that the cmdlet backs up only the certification authority database.

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

### -Incremental
Indicates that the cmdlet performs incremental database back up.

```yaml
Type: SwitchParameter
Parameter Sets: Database, All
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -KeepLog
Indicates that the cmdlet does not truncate database logs.

```yaml
Type: SwitchParameter
Parameter Sets: Database, All
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -KeyOnly
Indicates that the cmdlet backs up only the CA private key and certificate.

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
Specifies a password, as a secure string, to protect private key and certificate information.
To obtain a secure string, use the [ConvertTo-SecureString](https://go.microsoft.com/fwlink/?LinkID=113291) cmdlet.
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
Specifies the directory to which the cmdlet backs up the CA database and private key.
If you back up the database, the cmdlet creates a new subdirectory named Database that contains the database backup.
If you back up the private key, the cmdlet writes the private key to a .p12 file in the Database subdirectory in the path that you specify.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.Management.Automation.SwitchParameter

### System.Security.SecureString

## OUTPUTS

### System.Void

## NOTES

## RELATED LINKS

[ConvertTo-SecureString](https://go.microsoft.com/fwlink/?LinkID=113291)

[Restore-CARoleService](./Restore-CARoleService.md)

