---
external help file: ServerMig_Cmdlets.xml
Module Name: ServerMigrationCmdlets
online version: https://learn.microsoft.com/powershell/module/servermigrationcmdlets/receive-smigserverdata?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Receive-SmigServerData

## SYNOPSIS
Allows a destination server to receive shares, folders, files, and associated permissions and share properties that are migrated from a source server.
The cmdlet Send-SmigServerData must be run on the source server at the same time Receive-SmigServerData is running on the destination server.

## SYNTAX

```
Receive-SmigServerData [-Password] <SecureString>
```

## DESCRIPTION
Allows a destination server to receive, over port 7000, shares, folders, files, and associated permissions and share properties that are migrated from a source server.
The cmdlet Send-SmigServerData must be started on the source server to send data.
By default, the cmdlet Receive-SmigServerData can wait for a maximum of five minutes to establish a connection with the cmdlet Send-SmigServerData on the source server.
You can use a registry key to change the default maximum connection time; for more information about this registry setting, see the Notes.

In this release of Windows Server, you can send and receive data between servers that are not necessarily on the same subnets.
You can also specify IP addresses as the names of the source or destination servers.
To support migration across subnets, and migrate by specifying IP addresses, port numbers 7001 and 7002 must be opened on source and destination servers.

File access rights are maintained during the migration; the same set of users is able to access files on the destination server after they have been migrated.
Because files are sent by using an encrypted connection, a password must be provided to decrypt migrated files on both the source and destination servers.
Transporting encrypted files (EFS) and junction points is not supported.

For online Help about the Windows Server Migration Tools cmdlets, see http://go.microsoft.com/fwlink/?LinkId=246313.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
PS C:\> Receive-SmigServerData
```

Description

-----------

This sample command receives data that is migrated from a source computer by using the cmdlet Send-SmigServerData.
Because a password is not provided in this sample command, after entering the command, the user is prompted to enter a password for decrypting the migrated data.
Password characters are displayed as asterisks (*).When the password is entered, the value is passed to the command as a SecureString.

### -------------------------- EXAMPLE 2 --------------------------
```
PS C:\> Receive-SmigServerData -Password (Read-Host "Enter a Password:" -AsSecureString)
```

Description

-----------

This sample command receives data that is migrated from a source computer by using the cmdlet Send-SmigServerData.
The command also instructs the migration tools to display the string "Enter a Password:" to prompt users to enter the password to decrypt the migrated data.
Password characters are displayed as asterisks (*).
When the password is entered, the value is passed to the command as a SecureString.

### -------------------------- EXAMPLE 3 --------------------------
```
PS C:\> $pass = ConvertTo-SecureString -String "password" -AsPlainText -Force

C:\PS> Receive-SmigServerData -Password $pass
```

Description

-----------

In this example, the first line of the command instructs the migration utilities to convert the data decryption password, represented by "password," to a secure string, and store it in the variable $pass.

The second line of the sample command receives data that is migrated from a source computer by using the cmdlet Send-SmigServerData.
The second command also sets the value of the variable $pass, specified in the first command, as the password to decrypt the data transfer.

## PARAMETERS

### -Password
Use this parameter to specify the password, as a secure string, to decrypt the data transfer by using 256-bit advanced encryption standard (AES).
The secure string can be obtained by entering the command Read-Host -AsSecureString or ConvertTo-SecureString.

You must specify a password to protect your data because migrated data is broadcast over a network.
If the Password parameter is not added to your command, you are prompted to specify a password after entering your command.

```yaml
Type: SecureString
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES
* The Windows Server Migration Tools deployment log file is located in %windir%\Logs\SmigDeploy.log. Other Windows Server Migration Tools log files are created at the following locations:

- %windir%\Logs\ServerMigration.log

- On Windows Server 2008 and Windows Server 2008 R2: %localappdata%\SvrMig\Log

- On Windows Server 2003: %userprofile%\Local Settings\Application Data\SvrMig\Log

  If the log files cannot be created at these locations, ServerMigration.log and SmigDeploy.log will be created at %temp%, and other logs will be created at %windir%\System32.

  The maximum size of all log files (in MB) is stored in the following registry key.
When the log file grows larger than the size specified in the registry key, the log file is deleted.
Logging begins again in a new log file that uses the same file name and path.
The default maximum log size is 200 MB.

- Key: HKLM\Software\Microsoft\ServerMigration

- Value: MaxLogSize (REG_DWORD)

- Data: Whole numbers between 1 and 1000 (represents log size, in MB)

  The maximum connection time for Send-SmigServerData and Receive-SmigServerData cmdlet is stored in the following registry key.
Send-SmigServerData and Receive-SmigServerData operations stop if a connection cannot be established within the specified time.
The default maximum connection time is 300 seconds, or five minutes.

- Key: HKLM\Software\Microsoft\ServerMigration

- Value: MaxConnectionTime  (REG_DWORD)

-Data: Between 1 and 3600 (represents connection time, in seconds).
If a value larger than 3600 is specified, 3600 seconds is used as the maximum connection time.

## RELATED LINKS

