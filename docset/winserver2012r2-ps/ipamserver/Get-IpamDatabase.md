---
external help file: IpamDatabase.cdxml-help.xml
Module Name: IpamServer
ms.date: 10/30/2017
online version: https://docs.microsoft.com/powershell/module/ipamserver/get-ipamdatabase?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-IpamDatabase
---

# Get-IpamDatabase

## SYNOPSIS
Gets configuration settings for the IPAM database.

## SYNTAX

```
Get-IpamDatabase [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-IpamDatabase** cmdlet gets configuration settings for the IP Address Management (IPAM) database.
The cmdlet can get settings for Windows Internal Database (WID) or a Microsoft SQL Server database.

Use the Set-IpamDatabase cmdlet to modify settings IPAM uses to connect to a database.

You must be a local administrator on the IPAM server to run this cmdlet.

## EXAMPLES

### Example 1: Get IPAM database properties
```
PS C:\> Get-IpamDatabase
DatabaseType     : WID

WidSchemaPath    : C:\Windows\System32\ipam\Database

DatabaseServer   :

DatabaseName     : IPAM

DatabasePort     :

DatabaseAuthType : Windows

DatabaseUser     :
```

This command gets IPAM database properties.
In this example, the database type is WID.

### Example 2: Get IPAM database properties for an external database
```
PS C:\>Get-IpamDatabase
DatabaseType     : MSSQL

WidSchemaPath    :

DatabaseServer   : ContosoDB22

DatabaseName     : IpamDB1

DatabasePort     : 1433

DatabaseAuthType : Windows

DatabaseUser     :
```

This command gets IPAM database properties for an external database.
In this example, the database type is MSSQL.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### IpamDatabase
An object that represents the database settings used by IPAM to connect to the datastore.

## NOTES

## RELATED LINKS

[Move-IpamDatabase](./Move-IpamDatabase.md)

[Set-IpamDatabase](./Set-IpamDatabase.md)

