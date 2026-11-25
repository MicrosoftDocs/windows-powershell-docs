---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: IpamServerProvisioning.cdxml-help.xml
Module Name: IpamServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/ipamserver/invoke-ipamserverprovisioning?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-IpamServerProvisioning
---

# Invoke-IpamServerProvisioning

## SYNOPSIS
Automates the provisioning of IPAM server.

## SYNTAX

### WID (Default)
```
Invoke-IpamServerProvisioning [-WidSchemaPath <String>] [-ProvisioningMethod <ProvisioningMethod>]
 [-GpoPrefix <String>] [-Force] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### ExternalDatabase
```
Invoke-IpamServerProvisioning [-ProvisioningMethod <ProvisioningMethod>] [-GpoPrefix <String>] [-Force]
 [-DatabaseServer] <String> [-DatabaseName] <String> [-DatabasePort] <UInt16> [-DatabaseAuthType <AuthType>]
 [-DatabaseCredential <PSCredential>] [-UseExistingSchema] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Invoke-IpamServerProvisioning** cmdlet installs and configures IP Address Management (IPAM) server components on the host on which you run the cmdlet.
When you run the cmdlet locally on IPAM server or remotely from an RSAT, the cmdlet installs and configures IPAM components on the IPAM server to which the session is connected.
As a part of installation, the cmdlet performs the following functions:

1. Configures the WCF and WSMan settings, such as Port and App Pool configuration.

2. Creates and connects to an IPAM database.
   The cmdlet attempts to create a database by using authentication credentials that the user specifies.
   An error occurs if the database that you specify does not exist or the chosen credentials do not include permissions to create a database.

3. Creates IPAM Tasks to get data for IPAM views.

4. Creates default user roles for access control.
   This includes RBAC roles in the database and any local security groups.

5. Configures a provisioning method.

6. By default, the cmdlet enables all available IPAM optional capabilities.

You can choose to manually or automatically provision access to managed servers.
If you provisioned the managed servers by using group policy, make sure to create the corresponding GPOs in every managed domain by using the **Invoke-IpamGpoProvisioning** cmdlet.

## EXAMPLES

### Example 1: Provision an IPAM server
```
PS C:\> Invoke-IpamServerProvisioning
This cmdlet will provision IPAM on ipam1.contoso.com. As a part of provisioning, this cmdlet will provision IPAM to use Windows Internal database.
The cmdlet will create a new IPAM database at %WINDIR%\System32\IPAM\Database, create roles, and prepare IPAM for use.
Infrastructure servers managed by IPAM will have to be manually provisioned to provide access to IPAM. Read the product documentation for details.
Do you want to continue? Y
```

This command provisions an IPAM server with default settings.
By default, IPAM server uses the Windows Internal Database.
The database files are stored in the default location, %WINDIR%\System32\IPAM\Database.
The managed servers are provisioned manually by default.

### Example 2: Provision an IPAM server to use GPO-based provisioning
```
PS C:\> Invoke-IpamServerProvisioning -WidSchemaPath "D:\database" -ProvisioningMethod Automatic -GpoPrefix IPAM1
This cmdlet will provision IPAM on ipam1.contoso.com. As a part of provisioning, this cmdlet will provision IPAM to use Windows Internal database.
The cmdlet will create a new IPAM database at D:\database, create roles, and prepare IPAM for use.
IPAM will be configured to use Group Policy to provision the managed servers. Read the product documentation for details.
Do you want to continue?Y
```

This command provisions an IPAM server to use the Windows Internal Database and a GPO-based provisioning method for managed servers.
The command stores the database files at a custom location.

### Example 3: Provision an IPAM server to use Microsoft SQL Server
```
PS C:\> Invoke-IpamServerProvisioning -DatabaseServer "Db1.Contoso.com" -DatabaseName "Ipamdb" -DatabasePort 1433
This cmdlet will provision IPAM on ipam1.Contoso.com. As a part of provisioning, this cmdlet will provision IPAM to use Microsoft SQL Server on Db1.Contoso.com.
The cmdlet will create a new IPAM database, create roles, and prepare IPAM for use.
Infrastructure servers managed by IPAM will have to be manually provisioned to provide access to IPAM. Read the product documentation for details.
Do you want to continue?
```

This command provisions an IPAM server to use a Microsoft SQL Server database residing on a database server named Db1.Contoso.com.
The example assumes the existence of a server named Db1.Contoso.com, configured with Microsoft SQL Server, an empty database instance named Ipamdb, and the IPAM computer has access permissions for that database instance.

### Example 4: Provision an IPAM server to use a Microsoft SQL Server database provisioned by IPAM
```
PS C:\> $Credential = Get-Credential
PS C:\> Invoke-IpamServerProvisioning -DatabaseServer "Db1.Contoso.com" -DatabaseName "Ipamdb" -DatabasePort 1433 -ProvisioningMethod Automatic -GpoPrefix IPAM1 -DatabaseAuthType SQL -DatabaseCredential $Credential
This cmdlet will provision IPAM on ipam1.contoso.com. As a part of provisioning, this cmdlet will provision IPAM to use Microsoft SQL Server on db1.contoso.com.
The cmdlet will create a new IPAM database, create roles, and prepare IPAM for use.
IPAM will be configured to use Group Policy to provision the managed servers. Read the product documentation for details.
Do you want to continue?
```

The first command uses the **Get-Credential** cmdlet to get a credential, and stores the results in the $Credential variable.

The second command provisions an IPAM server to use a Microsoft SQL Server database that resides on a database server named Db1.Contoso.com.
The example assumes the existence of a server named Db1.Contoso.com, configured with Microsoft SQL Server, a database instance will be created by IPAM during provisioning, and the IPAM computer has db_datawriter, db_datareader, db_ddladmin, view database state, alter permissions on the database.

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
Specifies the type of authentication to use when connecting to the IPAM database.
If you specify Windows as the authentication type, IPAM uses the server computer account to connect to the database.
With SQL authentication, specify a username and password to connect to the database.

```yaml
Type: AuthType
Parameter Sets: ExternalDatabase
Aliases:
Accepted values: Windows, SQL

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DatabaseCredential
Specifies credentials, as a **PSCredential** object, for the computer that runs SQL Server.
To obtain a **PSCredential** object, use the **Get-Credential** cmdlet.
For more information, type `Get-Help Get-Credential`.

```yaml
Type: PSCredential
Parameter Sets: ExternalDatabase
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
Parameter Sets: ExternalDatabase
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DatabasePort
Specifies the port that the IPAM server uses to connect to the database server.

```yaml
Type: UInt16
Parameter Sets: ExternalDatabase
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DatabaseServer
Specifies the fully qualified domain name (FQDN) or IP address of the database server..
You can provide an IPv4 or IPv6 address, or a fully qualified domain name (FQDN).

```yaml
Type: String
Parameter Sets: ExternalDatabase
Aliases:

Required: True
Position: 1
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
Accept pipeline input: False
Accept wildcard characters: False
```

### -GpoPrefix
Specifies a unique Group Policy Object (GPO) prefix name that IPAM uses to create the group policy objects.
Use this parameter only when the *ProvisioningMethod* parameter has the value Automatic.

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

### -ProvisioningMethod
Specifies manual or automatic, GPO-based provisioning.
The acceptable values for this parameter are:Automatic and Manual.
In the case of manual provisioning, you must manually configure the managed servers to provide requisite access to IPAM.
In case of GPO-based, or automatic provisioning, you must create the GPOs in each of the managed domains through the **Invoke-IpamGpoProvisioning** cmdlet.
If you do not specify a provisioning method, it is assumed to be manual.

```yaml
Type: ProvisioningMethod
Parameter Sets: (All)
Aliases:
Accepted values: Automatic, Manual

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

### -UseExistingSchema
Indicates that the IPAM server uses an existing schema on the database server, instead of creating a schema.
An error occurs if this flag is specified and a valid schema is not found on the server.

```yaml
Type: SwitchParameter
Parameter Sets: ExternalDatabase
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

### -WidSchemaPath
Specifies the location on IPAM server where IPAM creates the Windows Internal Database (WID) schema.
To use an existing schema, specify the path to the folder containing the schema files.
If you do not specify a value for this parameter, IPAM tries to create the schema in the default path %SystemDrive%\Windows\System32\ipam\Database.

```yaml
Type: String
Parameter Sets: WID
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

## NOTES

## RELATED LINKS

[IP Address Management (IPAM) Server Cmdlets in Windows PowerShell](./ipamserver.md)

