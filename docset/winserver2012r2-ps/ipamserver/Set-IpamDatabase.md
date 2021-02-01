---
external help file: IpamDatabase.cdxml-help.xml
Module Name: IpamServer
online version: 
schema: 2.0.0
title: Set-IpamDatabase
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: FD58B36E-7689-4DD4-AFAD-A3CCA18D70DC
---

# Set-IpamDatabase

## SYNOPSIS
Modifies settings that IPAM uses to connect to the IPAM database.

## SYNTAX

```
Set-IpamDatabase [-DatabaseServer] <String> [-DatabaseName] <String> [-DatabasePort] <UInt16>
 -DatabaseAuthType <AuthType> [-DatabaseCredential <PSCredential>] [-PassThru] [-Force]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-IpamDatabase** cmdlet modifies settings that IP Address Management (IPAM) uses to connect to the IPAM database hosted on a computer that runs Microsoft SQL Server.

Verify that you can reach the database server from the IPAM server.
Specify whether to connect to the destination server by using the account for the computer that hosts the IPAM server or by using a SQL Server database account.
If you specify the IPAM server account, verify that account has necessary permissions.

Use the Get-IpamDatabase cmdlet to view database configuration settings.

You can specify any port to connect to the database server.
We recommend you use the default port, 1433, to connect to Microsoft SQL Server.

## EXAMPLES

### Example 1: Connect to an external database
```
The first command command uses the Get-IpamDatabase cmdlet to display the configuration settings of the database. 
PS C:\>Get-IpamDatabase
DatabaseType     : WID
WidSchemaPath    : C:\Windows\System32\IPAM\Database
DatabaseServer   : 
DatabaseName     : IPAM
DatabasePort     : 
DatabaseAuthType : Windows
DatabaseUser     : 


The second command sets the database configuration. The command includes the database name and database server name. The cmdlet prompts you before it continues.
PS C:\>Set-IpamDatabase -DatabaseServer "ContosoDB04" -DatabaseName "IpamData01" -DatabasePort 1433 -DatabaseAuthType Windows
Confirm
Updating IPAM database settings to use an MsSql database. If the configuration is successful, IPAM cannot be
reconfigured to use Windows Internal Database.  The cmdlet will verify that the database specified is reachable and
compatible with Ipam version. Do you want to continue? 
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): Y

The last command repeats the first command, displaying the revised configuration information. 
PS C:\>Get-IpamDatabase
DatabaseType     : MSSQL
WidSchemaPath    : 
DatabaseServer   : ContosoDB04
DatabaseName     : IpamData01
DatabasePort     : 1433
DatabaseAuthType : Windows
DatabaseUser     :
```

This example configures the IPAM server to connect to an external database.
The cmdlet does not move any data from the existing WID database or create the new database.
Configure all access settings manually on the database server.
The example uses Windows as the database authentication type.

## PARAMETERS

### -AsJob
ps_cimcommon_asjob

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
Enter a computer name or a session object, such as the output of a New-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
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
Specify this credential by using the **DatabaseCredential** parameter. 
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
The IPAM server connects to this database.

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
The IPAM server connects to this server.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### IpamDatabase
Represents the datastore for an IPAM server.

## NOTES

## RELATED LINKS

[Get-IpamDatabase](./Get-IpamDatabase.md)

[Move-IpamDatabase](./Move-IpamDatabase.md)

