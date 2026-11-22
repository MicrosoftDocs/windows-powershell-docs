---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Windows.ServerManager.PowerShell.dll-Help.xml
Module Name: Microsoft.Windows.ServerManager.Migration
ms.date: 01/03/2017
online version: https://learn.microsoft.com/powershell/module/microsoft.windows.servermanager.migration/export-smigserversetting?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Export-SmigServerSetting
---

# Export-SmigServerSetting

## SYNOPSIS
Exports selected Windows features and operating system settings from the local computer, and stores them in a migration store.

## SYNTAX

```
Export-SmigServerSetting [-FeatureId <String[]>] [-Feature <Feature[]>] [-User <String>] [-Group] [-IPConfig]
 -Path <String> -Password <SecureString> [<CommonParameters>]
```

## DESCRIPTION
The **Export-SmigServerSetting** cmdlet exports selected Windows features and operating system settings from the local computer, and stores them in a migration store specified in the *Path* parameter.
Use the Import-SmigServerSetting cmdlet to import Windows features and operating system settings to the destination computer from the migration store populated by the Export-SmigServerSetting command.

For online Help about the Windows Server Migration Tools cmdlets, see [Server Migration Cmdlets in Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=246313) at http://go.microsoft.com/fwlink/?LinkId=246313.

## EXAMPLES

### Example 1: Export the DHCP server
```
PS C:\> Export-SmigServerSetting -Feature "DHCP" -User All -Group -Path "c:\temp\store" -Verbose
```

This sample command exports the Dynamic Host Configuration Protocol (DHCP) server and all other Windows Server features that are required by the DHCP server.
The command also exports local user accounts, local groups, and group memberships to the location c:\temp\store that is specified in the *Path* parameter.

Creating a password to encrypt the migration store is required.
Because a password is not provided in this sample command, after you enter the command, the user is prompted to enter a password for encrypting the migrated data.
Password characters are displayed as asterisks (*).
When the password is entered, the value is passed to the command as a SecureString.

By using the *Verbose* parameter, the command also displays detailed information about the migration operation.

### Example 2: Export IP configuration settings
```
PS C:\> Export-SmigServerSetting -IPConfig -Path "c:\temp\store" -Password (Read-Host "Create a Password:" -AsSecureString) -Verbose
```

This sample command exports basic IP configuration settings, and stores the data in the migration store specified by the *Path* parameter as c:\temp\store.
The sample command also instructs the migration utilities to display the text string "Create a Password:" to prompt the user to create a password for encrypting the migration store.
Password characters are displayed as asterisks (*).
When the new password has been entered, the value is stored by **Export-SmigServerSetting** as a SecureString.

By using the *Verbose* parameter, the command also displays detailed information about the migration operation.

### Example 3: Export Windows Server features
```
PS C:\> $c = Get-SmigServerFeature
PS C:\> Export-SmigServerSetting -Feature $c -Path "c:\temp\store" -Verbose
```

This sample command exports a set of Windows features that have already been specified by using the Get-SmigServerFeature cmdlet.
In the sample, the migration utilities are instructed to use a variable, $c, to represent the features specified by using the **Get-SmigServerFeature** cmdlet.

The first command retrieves Windows feature objects specified by using the **Get-SmigServerFeature** cmdlet, and saves them in the $c variable.
The second command exports the Windows features represented by the $c variable, and stores the data in the location that is specified in the *Path* parameter, c:\temp\store.

Creating a password to encrypt the migration store is required.
Because a password is not provided in this sample command, after entering the command, the user is prompted to enter a password for encrypting the migrated data.
Password characters are displayed as asterisks (*).
When the password is entered, the value is passed to the command as a SecureString.

By using the *Verbose* parameter, the command also displays detailed information about the migration operation.

### Example 4: Export user accounts
```
PS C:\> $pass = ConvertTo-SecureString -String "password" -AsPlainText -Force
PS C:\> Export-SmigServerSetting -User All -Password $pass -Path "c:\store" -Verbose
```

In this example, the first command instructs the migration utilities to convert the store encryption password, represented by "password," to a secure string, and store it in the variable $pass.
The second command exports all local user accounts, sets the value of the variable $pass as the password to encrypt the migration store, and stores the migration data in the location c:\temp\store.

By using the *Verbose* parameter, the command also displays detailed information about the migration operation.

## PARAMETERS

### -Feature
Specifies the Windows features to be exported from the source computer.
Not all Windows features can be migrated by using migration cmdlets.
You can use the Get-SmigServerFeature cmdlet to retrieve a list of Windows features that can be migrated from the local server, and pass the resulting list to the **Export-SmigServerSetting** cmdlet, either by piping the results to the cmdlet, or by storing the results in a variable and then using the variable to represent the results in your command.

```yaml
Type: Feature[]
Parameter Sets: (All)
Aliases: F

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -FeatureId
Specifies the IDs of the Windows features to be exported from the source computer.
Not all Windows features are supported for migration.
You can use the **Get-SmigServerFeature** cmdlet to retrieve a list of Windows features, along with their feature IDs, that can be migrated from the local server.
Separate multiple feature IDs by using commas.
Standard PowerShell wildcard characters are supported.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: ID

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Group
Exports the source server's local groups.

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

### -IPConfig
Exports the source server's basic IP configuration settings, including network interface card (NIC) settings such as connection-specific suffix, IPv4 settings, registry key to disable IPv6 components, and global Windows IP configuration settings.
IP configuration for a NIC can only be exported if the NIC is enabled and connected to the network.
See IP Configuration Migration Guide for more information.

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

### -Password
Specifies the migration store encryption password as a secure string.
The secure string can be obtained by entering the command `Read-Host -AsSecureString` or `ConvertTo-SecureString`.
Because the *Password* parameter is required, if it is not added to your command, you are prompted to create a password after entering your command.
The password length must be a minimum of six characters and a maximum of 260 characters.

```yaml
Type: SecureString
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path
Specifies the path to store the exported migration data.
The specified migration store location must be empty.
The path must be a valid local or Universal Naming Convention (UNC) path; if it is a share on a remote computer, the share must be notated as a drive letter on the local computer.
The path length cannot be longer than 246 characters.
Wildcard characters are not supported.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -User
Specifies the type of user accounts to export to the migration store.
The following are acceptable values for this parameter:


- Enabled

- Disabled

- All

User passwords are not migrated.
Users must create a password the first time they log on to the server.
Only the "User Name" and "Account is Disabled" properties are migrated.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Windows.ServerManager.Migration.MigrationResult

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

[Import-SmigServerSetting](./Import-SmigServerSetting.md)

