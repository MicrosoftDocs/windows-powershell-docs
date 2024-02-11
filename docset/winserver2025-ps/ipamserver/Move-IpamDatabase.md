---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: IpamDatabase.cdxml-help.xml
Module Name: IpamServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/ipamserver/move-ipamdatabase?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Move-IpamDatabase
---

# Move-IpamDatabase

## SYNOPSIS
Migrates the IPAM database to a SQL Server database.

## SYNTAX

```
Move-IpamDatabase [-DatabaseServer] <String> [-DatabaseName] <String> [-DatabasePort] <UInt16>
 -DatabaseAuthType <AuthType> [-DatabaseCredential <PSCredential>] [-PassThru] [-Force]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Move-IpamDatabase** cmdlet migrates the IP Address Management (IPAM) database to a Microsoft SQL Server database.
You can migrate from Windows Internal Database (WID) or from a SQL Server database.
The cmdlet creates a new IPAM schema and copies all data from the existing IPAM database.
After the cmdlet completes copying data, it changes IPAM configuration settings to refer to the new database as the IPAM database.
If you migrate from WID, the cmdlet renames the existing data and log files by appending a time stamp to the file names.

If the cmdlet cannot complete the migration for any reason, it returns an error and does not change the current database settings.

Verify that you can reach the database server from the IPAM server.
Specify whether to connect to the destination server by using the account for the computer that hosts the IPAM server or by using a SQL Server database account.
If you specify the IPAM server account, verify that the account has permissions necessary to write to the destination database.
If the migration requires a new database, verify that the account has permissions to create and write to the database.

Use the **Get-IpamDatabase** cmdlet to view database configuration settings.

We recommend that you isolate the IPAM server and shut down all IPAM clients before you migrate a database.

The collation of the source and destination databases should be the same.
If the destination database is not present, this cmdlet creates a new database using the default collation for the destination SQL Server.
This might cause errors if the default collation of the source SQL database is different.
To avoid this, use the following steps to manually create the destination database.

Moving from WID to an external SQL Server

Create the destination database on external SQL Server by using the following command:

`CREATE DATABASE \[\<DBName\>\] COLLATE \<DB collation name\>`The parameter 'DB collation name' should be specified as **SQL_LATIN1_GENERAL_CP1_CI_AS** in this case.

Moving from one SQL Server database to another external SQL Server database

Read the collation of the existing database by using the following command:

`SELECT collation_name FROM sys.databases WHERE name = N'\<DBName\>'`

Create a new database on the destination SQL server by using the following command:

`CREATE DATABASE \[\<DBName\>\] COLLATE \<DB collation name\>`

## EXAMPLES

### Example 1: Move an IPAM database
```
This command uses the **Get-IpamDatabase** cmdlet to get the database configuration information. The console displays configuration information, including the type of database, WID.
PS C:\> Get-IpamDatabase
DatabaseType     : WID

WidSchemaPath    : C:\Windows\System32\IPAM\DataBase

DatabaseServer   :

DatabaseName     : IPAM

DatabasePort     :

DatabaseAuthType : Windows

DatabaseUser     :


This command moves the IPAM data to a database named IpamDB1 on the server named ContosoDB22. The database uses port 1433. The command specifies Windows as the authentication type, so the command uses credentials for the IPAM server. The cmdlet prompts you for confirmation.
PS C:\> Move-IpamDatabase -DatabaseServer "ContosoDB22" -DatabaseName "IpamDB1" -DatabasePort 1433 -DatabaseAuthType Windows
Confirm

This command will migrate IPAM data to the specified MsSql Database. The cmdlet will create a new Ipam Schema, copy the data and configure IPAM to use the new database. Once this migration is completed successfully, you will not be able to revert to using Windows Internal Database. Do you want to continue?

[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): Y


This command uses the **Get-IpamDatabase** cmdlet to get the database configuration information. The console displays configuration information, including the type of database, WID. The console displays configuration information, including the type of database, now MSSQL. The database now has values for **DatabaseServer**, **DatabaseName**, and **DatabasePort**, as specified in the second command.
PS C:\> Get-IpamDatabase
DatabaseType     : MSSQL

WidSchemaPath    :

DatabaseServer   : ContosoDB22

DatabaseName     : IpamDB1

DatabasePort     : 1433

DatabaseAuthType : Windows

DatabaseUser     :
```

This example moves an IPAM database to a database named IpamDB1 on a database server named ContosoDB22.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

The cmdlet immediately returns an object that represents the job and then displays the command prompt.
You can continue to work in the session while the job completes.
To manage the job, use the `*-Job` cmdlets.
To get the job results, use the [Receive-Job](https://go.microsoft.com/fwlink/?LinkID=113372) cmdlet.

For more information about Windows PowerShell background jobs, see [about_Jobs](https://go.microsoft.com/fwlink/?LinkID=113251).

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

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
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

### -DatabaseAuthType
Specifies which type of authentication to use to connect to the computer that runs SQL Server.
The acceptable values for this parameter are:

- SQL.
Use the database account.
Specify this credential by using the *DatabaseCredential* parameter.
- Windows.
Use the account for the computer that runs the IPAM server.

```yaml
Type: AuthType
Parameter Sets: (All)
Aliases:
Accepted values: Windows, SQL

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DatabaseCredential
Specifies credentials, as a **PSCredential** object, for the computer that runs SQL Server.
To obtain a **PSCredential** object, use the **Get-Credential** cmdlet.
For more information, type `Get-Help Get-Credential`.

Specify this parameter if you specified a value of SQL for the **DatabaseAuthType** parameter.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DatabaseName
Specifies the name of a SQL Server database.
The cmdlet migrates the IPAM database to this database.
If the database does not exist, IPAM creates a database that has this name on the destination server.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DatabasePort
Specifies the port that the IPAM server uses to connect to the database server.

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DatabaseServer
Specifies the fully qualified domain name (FQDN) or IP address of the database server.
The cmdlet migrates the IPAM database to this server.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
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
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

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

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell® calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
The throttle limit applies only to the current cmdlet, not to the session or to the computer.

```yaml
Type: Int32
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-IpamDatabase](./Get-IpamDatabase.md)

[Set-IpamDatabase](./Set-IpamDatabase.md)

