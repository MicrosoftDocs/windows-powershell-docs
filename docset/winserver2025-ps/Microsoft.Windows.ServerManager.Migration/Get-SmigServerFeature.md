---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Windows.ServerManager.PowerShell.dll-Help.xml
Module Name: Microsoft.Windows.ServerManager.Migration
ms.date: 01/03/2017
online version: https://learn.microsoft.com/powershell/module/microsoft.windows.servermanager.migration/get-smigserverfeature?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-SmigServerFeature
---

# Get-SmigServerFeature

## SYNOPSIS
Gets the set of all Windows features that can be migrated from the local server or from a migration store.

## SYNTAX

### empty (Default)
```
Get-SmigServerFeature [<CommonParameters>]
```

### TargetPreview
```
Get-SmigServerFeature -Path <String> -Password <SecureString> [<CommonParameters>]
```

## DESCRIPTION
The **Get-SmigServerFeature** cmdlet gets the set of all Windows Server features that can be migrated from the local server or from a migration store.
If a migration store is specified in the *Path* parameter, this cmdlet returns only the features in the migration store that can be installed on the local server.

For online Help about the Windows Server Migration Tools cmdlets, see [Server Migration Cmdlets in Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=246313) at http://go.microsoft.com/fwlink/?LinkId=246313.

## EXAMPLES

### Example 1: Get all Windows Server features
```
PS C:\> Get-SmigServerFeature
```

This command displays all Windows features that can be migrated from the local computer.

### Example 2: Get Windows Server features at a specified path
```
PS C:\> Get-SmigServerFeature -Path "c:\temp\store"
```

This command retrieves and displays the set of Windows features that can be migrated from the migration store specified by the *Path* parameter as located at c:\temp\store.
Because a password is not provided in this sample command, after entering the command, the user is prompted to provide a password for decrypting the migration store.
Password characters are displayed as asterisks (*).
When the password is entered, the value is passed to the command as a SecureString.

### Example 3: Get Windows Server features and display a password prompt
```
PS C:\> $c = Get-SmigServerFeature -Path "c:\temp\store" -Password (Read-Host "Enter a Password:" -AsSecureString)
```

The first line of the command uses the **Get-SmigServerFeature** cmdlet to retrieve role or feature objects from the migration store in the location specified by the *Path* parameter, and save them in the $c variable.

The command also instructs the migration tools to display the string "Enter a Password:" to prompt users to enter the password to decrypt the migration store.
Password characters are displayed as asterisks (*).
When the password is entered, the value is passed to the command as a SecureString.

### Example 4: Get Windows Server features and import them
```
PS C:\> Get-SmigServerFeature -Path "c:\temp\store" | Import-SmigServerSetting -Path "c:\temp\store" -Verbose
```

The first part of the command, before the pipe (|) character, retrieves all role or feature objects listed by using the **Get-SmigServerFeature** cmdlet that are found in the store specified by the *Path* parameter.
The second part of the command imports those Windows features that are both listed by **Get-SmigServerFeature** and available in the migration store.

Because a password is not provided in this sample command, after entering the command, the user is prompted to enter a password to decrypt the migration store.
Password characters are displayed as asterisks (*).
When the password is entered, the value is passed to the command as a SecureString.

By using the *Verbose* parameter, the command also displays detailed information about the migration operation.

### Example 5: Create a secure password variable to get Windows Server features and import them
```
PS C:\> $pass = ConvertTo-SecureString -String "password" -AsPlainText -
PS C:\> Get-SmigServerFeature -Path "c:\temp\store" -Password $pass | Import-SmigServerSetting -Path "c:\temp\store" -Password $pass -Verbose
```

The first command converts the store encryption password, represented by "password," to a secure string, and stores it in the variable $pass.

The second command has two parts.
The first, by using the **Get-SmigServerFeature** cmdlet, retrieves the set of Windows features that can be migrated from the migration store specified by the *Path* parameter as located at c:\temp\store, and provides the password to decrypt the migration store as represented by the variable $pass.
The second part of the command pipes the Windows features retrieved by the Get cmdlet to the Import-SmigServerSetting cmdlet for installation on a destination computer.
This command also supplies the password to decrypt the migration store, in the variable $pass.

By using the *Verbose* parameter, the command also displays detailed information about the migration operation.

## PARAMETERS

### -Password
Specifies the password, as a secure string, to decrypt the migration store.
The secure string can be obtained by entering the command `Read-Host -AsSecureString` or `ConvertTo-SecureString`.

```yaml
Type: SecureString
Parameter Sets: TargetPreview
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path
Specifies the path to the migration store from which you want to retrieve Windows features.
The path must be a well-formed local or Universal Naming Convention (UNC) path; if it is a share on a remote computer, the share must be notated as a drive letter on the local computer.
The path length cannot be longer than 246 characters.
Wildcard characters are not supported.
The returned list of Windows features contains only those Windows features that are both in the migration store and installable on the local computer.

```yaml
Type: String
Parameter Sets: TargetPreview
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Windows.ServerManager.Migration.Feature[]
Gets the set of all Windows features that can be migrated from the local server or from a migration store.
If a migration store is specified in the *Path* parameter, this cmdlet returns only the features in the migration store that can be installed on the local server.

## NOTES
* The Windows Server Migration Tools deployment log file is located in %windir%\Logs\SmigDeploy.log. Other Windows Server Migration Tools log files are created at the following locations:


- %windir%\Logs\ServerMigration.log

- On Windows Server 2008 and later versions: %localappdata%\SvrMig\Log

- On Windows Server 2003: %userprofile%\Local Settings\Application Data\SvrMig\Log

  If the log files cannot be created at these locations, ServerMigration.log and SmigDeploy.log will be created at %temp%, and other logs will be created at %windir%\System32.

  The maximum size of all log files (in MB) is stored in the following registry key.
When the log file grows larger than the size specified in the registry key, the log file is deleted.
Logging begins again in a new log file that uses the same file name and path.
The default maximum log size is 200 MB.


- Key: HKLM\Software\Microsoft\ServerMigration

- Value: MaxLogSize (REG_DWORD)

- Data: Whole numbers between 1 and 1000 (represents log size, in MB)

## RELATED LINKS

