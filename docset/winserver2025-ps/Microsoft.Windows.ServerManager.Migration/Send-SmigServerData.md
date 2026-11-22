---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Windows.ServerManager.PowerShell.dll-Help.xml
Module Name: Microsoft.Windows.ServerManager.Migration
ms.date: 01/03/2017
online version: https://learn.microsoft.com/powershell/module/microsoft.windows.servermanager.migration/send-smigserverdata?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Send-SmigServerData
---

# Send-SmigServerData

## SYNOPSIS
Migrates folders, files, and associated permissions and share properties from a source server to a destination server through port 7000.
The cmdlet Receive-SmigServerData must be run on the destination server at the same time Send-SmigServerData is running on the source server.

## SYNTAX

```
Send-SmigServerData -ComputerName <String> -Password <SecureString> -Include <MigrationIncludeTypes>
 -DestinationPath <String> [-Force] [-Recurse] -SourcePath <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Send-SmigServerData** cmdlet migrates folders, files, and associated permissions and share properties from the local server to a destination server through port 7000.
The cmdlet Receive-SmigServerData must be started on the destination server to receive data.
By default, the cmdlet **Send-SmigServerData** can wait for a maximum of five minutes to establish a connection with the cmdlet **Receive-SmigServerData** on the destination server.
You can use a registry key to change the default maximum connection time; for more information about this registry setting, see the Notes.

In this release of Windows Server, you can send and receive data between servers that are not necessarily on the same subnets.
You can also specify IP addresses as the names of the source or destination servers.
To support migration across subnets, and migrate by specifying IP addresses, port numbers 7001 and 7002 must be opened on source and destination servers.

File access rights are maintained during the migration; the same set of users is able to access files on the destination server after they have been migrated.
Because files are sent by using an encrypted connection, a password must be provided to decrypt migrated files on both the source and destination servers.
Transporting encrypted files (EFS) and junction points is not supported.

For online Help about the [Server Migration Cmdlets in Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=246313) at http://go.microsoft.com/fwlink/?LinkId=246313.

## EXAMPLES

### Example 1: Send files
```
PS C:\> Send-SmigServerData -Include Data -ComputerName "Server2" -SourcePath "c:\users" -DestinationPath "d:\shares\users" -Verbose
```

This sample command migrates all files from the folder c:\users on the local (source) computer to the folder d:\shares\users on the destination computer.
By default, subfolders in c:\users are not transferred.
The command uses the computer name Server2, as provided in the *ComputerName* parameter, to find the destination server in the subnet.

Because a password is not provided in this sample command, after entering the command, the user is prompted to enter a password for encrypting the migrated data.
Password characters are displayed as asterisks (*).When the password is entered, the value is passed to the command as a SecureString.

By using the *Verbose* parameter, the command also displays detailed information about the migration operation.

### Example 2: Create a password variable and use it to send files
```
PS C:\> $pass = ConvertTo-SecureString -String "password" -AsPlainText -Force
PS C:\> Send-SmigServerData -Include Share -ComputerName "Server2" -SourcePath "c:\users" -DestinationPath "d:\shares\users" -Recurse -Password $pass -Verbose
```

In this example, the first line of the command instructs the migration utilities to convert the data encryption password, represented by "password," to a secure string, and store it in the variable $pass.

The second sample command migrates only share status and permissions for folder c:\users and for all subfolders by using the *Include* and *Recurse* parameters.
The files and subfolders in folder c:\users are not migrated.
This command also sets the value of the variable $pass, specified in the first command, as the password to encrypt the data transfer.
The command uses the computer name Server2, as provided in the *ComputerName* parameter, to find the destination server in the subnet.

By using the *Verbose* parameter, the command also displays detailed information about the migration operation.

### Example 3: Send files and include subfolders
```
PS C:\> Send-SmigServerData -Include All -ComputerName "Server2" -SourcePath "c:\users" -DestinationPath "d:\shares\users" -Recurse -Password (Read-Host "Enter a Password:" -AsSecureString) -Verbose
```

In this example, the command migrates all migration data in the folder C:\users on the local server to the folder D:\shares\users on a remote server, Server2.
Because the *Recurse* parameter has been added, the command also migrates data that is stored in subfolders of the source folder.
To encrypt the data as it is transferred to the destination server, the *Password* parameter is added.
The value of the *Password* parameter is actually a second command, `(Read-Host "Enter a Password:" -AsSecureString)`, to prompt the administrator to provide a password, and encrypt the provided password as a secure string.
Finally, the *Verbose* parameter is added to display full details about the actions and progress of the command.

## PARAMETERS

### -ComputerName
Specifies the name or IP address of the destination server to which you want to copy data.

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

### -DestinationPath
Specifies the path on the destination server to which you want to copy data.
To avoid migration failures, verify that the destination path you specify exists for share-only migration.
For other migration types, verify that the path can be created on the destination computer.
The path must be a valid local path.
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

### -Force
Overwrites existing files automatically if the files that you are migrating from the source server are newer.
Also overwrites existing shares' properties if the shares' names already exist on the source server.

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

### -Include
Specifies the type of content to copy to the destination server.
The following are acceptable values for this parameter:


- Data: Copies only files in the folder designated by the *SourcePath* parameter to the folder designated by the *DestinationPath* parameter.
Subfolders and their content are not copied unless the *Recurse* parameter is added.

- Share: Copies only the share properties assigned to the folder specified in the *SourcePath* parameter to the folder specified in the *DestinationPath* parameter.
For example, if a folder was shared on the source server, it is shared on the destination server if the Share value is provided in the cmdlet, thereby preserving all share properties and permissions.
Share properties for subfolders and their content are not copied unless the *Recurse* parameter is added.
The files and subfolders in the folder designated by *SourcePath* are not migrated.
To avoid migration failures, verify that the folder specified in the *DestinationPath* parameter (and all subfolders if the *Recurse* parameter is added) exists.
- All: Copies both data and associated share properties.

```yaml
Type: MigrationIncludeTypes
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Password
Specifies the password, as a secure string, to encrypt the data transfer by using the 256-bit advanced encryption standard (AES).
The secure string can be obtained by entering the command `Read-Host -AsSecureString` or `ConvertTo-SecureString`.

You must specify a password to protect your data because transferred data is broadcast over a network.
If the *Password* parameter is not added to your command, you are prompted to specify a password after entering your command.
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

### -Recurse
Copies all content of the type specified by *Include* parameter in the path specified in the *SourcePath* parameter.
If this parameter is not used, subfolders of the *SourcePath* are not copied.

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

### -SourcePath
Specifies the folder on the source server from which you want to copy data.
To avoid migration failures, it is required that you first verify that the source path you specify exists on the source computer, except in the case of share-only migration.
The path must be a valid local path.
The path length cannot be longer than 246 characters.
Wild card characters are not supported.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Windows.ServerManager.Migration.Commands.MigrationResult []
A **MigrationResult** object contains basic information about the success or failure of a requested migration item.

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

  The maximum connection time for **Send-SmigServerData** and **Receive-SmigServerData** cmdlet is stored in the following registry key.
**Send-SmigServerData** and **Receive-SmigServerData** operations terminate if a connection cannot be established within the specified time.
The default maximum connection time is 300 seconds, or five minutes.


- Key: HKLM\Software\Microsoft\ServerMigration

- Value: MaxConnectionTime  (REG_DWORD)

- Data: Between 1 and 3600 (represents connection time, in seconds).
If a value larger than 3600 is specified, 3600 seconds is used as the maximum connection time.

## RELATED LINKS

[Receive-SmigServerData](./Receive-SmigServerData.md)

