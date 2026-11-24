---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Windows.ServerManager.PowerShell.dll-Help.xml
Module Name: Microsoft.Windows.ServerManager.Migration
ms.date: 01/03/2017
online version: https://learn.microsoft.com/powershell/module/microsoft.windows.servermanager.migration/import-smigserversetting?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Import-SmigServerSetting
---

# Import-SmigServerSetting

## SYNOPSIS
Imports selected Windows features, and operating system settings from a migration store, and applies them to the local computer.

## SYNTAX

```
Import-SmigServerSetting [-Feature <Feature[]>] [-FeatureId <String[]>] [-Group]
 [-SourcePhysicalAddress <String[]>] [-TargetPhysicalAddress <String[]>] [-Force] -Path <String>
 [-User <String>] [-IPConfig <String>] -Password <SecureString> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Import-SmigServerSetting** cmdlet imports selected Windows features and operating system settings from a migration store identified in the *Path* parameter, and applies them to the local computer.
Before running this cmdlet, you must first use the Export-SmigServerSetting cmdlet to export Windows features, and settings from a source server to the migration store.
The order in which settings are applied is not guaranteed.
To migrate settings that must be migrated in sequential order, run the **Import-SmigServerSetting** cmdlet multiple times to apply the settings in the required order.
You can also use this cmdlet to install Windows features and their dependencies, if the Windows features you are migrating have not been installed.
Some Windows features might require that the destination computer be restarted to complete installation.
After restarting the computer, you must run the cmdlet again with *Force* parameter to complete the import operation.

For online Help about the Windows Server Migration Tools cmdlets, see [http://go.microsoft.com/fwlink/?LinkId=246313](https://go.microsoft.com/fwlink/?LinkId=246313).

## EXAMPLES

### Example 1: Import a DHCP server
```
PS C:\> Import-SmigServerSetting -Feature "DHCP" -User All -Group -Path "c:\temp\store" -Verbose
```

This sample command imports the Dynamic Host Configuration Protocol (DHCP) server, and all other Windows features required by this technology.
The command also import local user accounts, local groups, and group memberships to the location c:\temp\store that is specified in the *Path* parameter.

Entering the password to decrypt the migration store is required.
Because a password is not provided in this sample command, after you enter the command, the user is prompted to enter a password for encrypting the migrated data.
Password characters are displayed as asterisks (*).
When the password is entered, the value is passed to the command as a SecureString.

By using the *Verbose* parameter, the command also displays detailed information about the migration operation.

### Example 2: Import an IP configuration
```
PS C:\> Import-SmigServerSetting -IPConfig All -SourcePhysicalAddress "00-13-D3-F7-A1-3A","00-13-D3-F7-A1-4A" -TargetPhysicalAddress "11-13-D3-F7-A1-3A","11-13-D3-F7-A1-4A" -Path "c:\temp\store" -Password (Read-Host "Enter a Password:" -AsSecureString)-Verbose
```

This command imports the IP configuration from the migration store specified at c:\temp\store, and applies it to the local server.
The IP configuration from the network interface card (NIC) with the physical address 00-13-D3-F7-A1-3A is migrated to the NIC with the physical address 11-13-D3-F7-A1-3A, and from the NIC with the physical address 00-13-D3-F7-A1-4A to the NIC with the physical address 11-13-D3-F7-A1-4A.
This command also instructs the migration tools to import Windows IP configuration settings such as DNS Suffix Search List settings and Disable IPv6 registry key value.

The command also instructs the migration tools to display the string "Enter a Password:" to prompt users to enter the password to decrypt the migration store.
Password characters are displayed as asterisks (*).
When the password is entered, the value is passed to the command as a SecureString.

By using the *Verbose* parameter, the command also displays detailed information about the migration operation.

### Example 3: Get Windows Server features and import them
```
PS C:\> $c = Get-SmigServerFeature -Path "c:\temp\store"
PS C:\> Import-SmigServerSetting -Feature $c -Path "c:\temp\store" -Verbose
```

This command imports a set of Windows features that have already been retrieved by using the Get-SmigServerFeature cmdlet.

The first line of the command retrieves role or feature objects specified by using the **Get-SmigServerFeature** cmdlet, and saves them in the $c variable.
The second line of the command imports the Windows features represented by the $c variable from the migration store that is specified in the *Path* parameter, c:\temp\store.

Entering the password to decrypt the migration store is required.
Because a password is not provided in this sample command, after you enter the command, the user is prompted to enter a password for encrypting the migrated data.
Password characters are displayed as asterisks (*).
When the password is entered, the value is passed to the command as a SecureString.

By using the *Verbose* parameter, the command also displays detailed information about the migration operation.

### Example 4: Get Windows Server features and import them
```
PS C:\> Get-SmigServerFeature -Path "c:\temp\store" | Import-SmigServerSetting -Path "c:\temp\store" -Verbose
```

This command pipes a set of features that have already been retrieved by using the Get-SmigServerFeature cmdlet to the **Import-SmigServerSetting** cmdlet.

The first part of the command, before the pipe (|) character, retrieves all role or feature objects listed by using the **Get-SmigServerFeature** cmdlet that are found in the store specified by the *Path* parameter.
The second part of the command imports those Windows features that are both listed by **Get-SmigServerFeature** and available in the migration store.

Entering the password to decrypt the migration store is required.
Because a password is not provided in this sample command, after you enter the command, the user is prompted to enter a password for encrypting the migrated data.
Password characters are displayed as asterisks (*).
When the password is entered, the value is passed to the command as a SecureString.

By using the *Verbose* parameter, the command also displays detailed information about the migration operation.

### Example 5: Create a password variable and use it to import user accounts
```
PS C:\> $pass = ConvertTo-SecureString -String "password" -AsPlainText -Force
PS C:\> Import-SmigServerSetting -User All -Password $pass -Path "c:\store" -Verbose
```

In this example, the first command converts the store encryption password, represented by "password," to a secure string, and stores it in the variable $pass.
The second command imports all local user accounts, uses the value of the variable $pass as the password to decrypt the migration store.

By using the *Verbose* parameter, the command also displays detailed information about the migration operation.

## PARAMETERS

### -Feature
Specifies the Windows feature objects that you want to import from the migration store.
Not all Windows features can be migrated by using migration cmdlets.
You can use the Get-SmigServerFeature cmdlet to retrieve a list of Windows features that can be migrated from the migration store to the destination server, and pass the resulting list to the **Import-SmigServerSetting** cmdlet, either by piping the results to the cmdlet, or by storing the results in a variable and then using the variable to represent the results in your command.

This cmdlet also installs Windows features and their dependencies, if the features you are migrating have not been installed.
Some Windows features might require that the destination computer be restarted to complete installation.
After restarting the computer, you must run the cmdlet again with the *Force* parameter to complete the import operation.

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
Specifies the IDs of the Windows features that you want to import from the migration store.
Not all Windows features are supported for migration.
You can use the **Get-SmigServerFeature** cmdlet to retrieve a list of Windows features, along with their feature IDs, which can be migrated from the migration store to the destination server.
Separate multiple feature IDs by using commas.
Standard PowerShell wildcard characters are supported.

This cmdlet also installs Windows features and their dependencies, if the features you are migrating have not been installed.
Some Windows features might require that the destination computer be restarted to complete installation.
After restarting the computer, you must run the cmdlet again with the *Force* parameter to complete the import operation.

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

### -Force
Specifies that imported settings overwrite existing Windows feature settings on the destination computer.
If this parameter is not used, by default, existing Windows feature settings on the destination computer are preserved.

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

### -Group
Imports the local groups and their memberships from the migration store.
If a group already exists on the destination server, it is not overwritten.
Group memberships from the source server are added to existing groups on the destination server, and the existing group memberships on the destination server are preserved.

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
Imports the source server's basic IP configuration settings.
The following are acceptable values for this parameter:


- NIC: network interface card (NIC) IP configuration settings such as connection-specific suffix, IPv4 settings and Disable IPv6 Component registry key.
IP configuration can only be imported for a NIC if it is enabled and connected to the network.
You must restart your computer for disabling IPv6 components to take effect.

- Global: Windows IP configuration settings for the local computer.

- All: both NIC and Global settings.

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

### -Password
Specifies the password, as a secure string, to decrypt the migration store.
The secure string can be obtained by entering the command `Read-Host -AsSecureString` or `ConvertTo-SecureString`.
Because the *Password* parameter is required, if it is not added to your command, you are prompted to specify a password after entering your command.

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
Specifies the path to the migration store from which you want to import Windows features and operating system settings.
The path must be a well-formed local or Universal Naming Convention (UNC) path; if it is a share on a remote computer, the share must be notated as a drive letter on the local computer.
The path length cannot be longer than 246 characters.
Wildcard characters are not supported.
Because the *Path* parameter is required, if it is not added to your command, you are prompted to specify a path after entering your command.

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

### -SourcePhysicalAddress
Specifies, in double quotations, the physical addresses of the source network interface cards (NICs) from which to import IP settings.
To specify multiple source physical addresses, use commas to separate each address.
The number of source physical addresses must be the same as the number of destination physical addresses specified in the *TargetPhysicalAddress* parameter.
Wildcard characters are not supported.
This parameter is required when migrating NIC or all IP configurations.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetPhysicalAddress
Specifies, in double quotations, the physical addresses of the destination network interface cards (NICs) to which you want to apply IP settings.
If you specify multiple destination physical addresses, use commas to separate each address.
The number of destination physical addresses must be the same as the number of source physical addresses specified in the *SourcePhysicalAddress* parameter.
Wildcard characters are not supported.
This parameter is required when migrating NIC or all IP configurations.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -User
Specify the type of local user accounts to import from the migration store.
The following are acceptable values for this parameter:


- Enabled: import only enabled local users

- Disabled: import only disabled local users

- All: import both enabled and disabled local users

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Windows.ServerManager.Migration.MigrationResult []

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

[Export-SmigServerSetting](./Export-SmigServerSetting.md)

