---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/activedirectory/move-addirectoryserver?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Move-ADDirectoryServer
---

# Move-ADDirectoryServer

## SYNOPSIS
Moves a directory server in Active Directory to a new site.

## SYNTAX

```
Move-ADDirectoryServer [-WhatIf] [-Confirm] [-AuthType <ADAuthType>] [-Credential <PSCredential>]
 [-Identity] <ADDirectoryServer> [-Server <String>] [-Site] <ADReplicationSite> [<CommonParameters>]
```

## DESCRIPTION
The **Move-ADDirectoryServer** cmdlet moves a directory server in Active Directory to a new site within the same domain.

The *Identity* parameter specifies the directory server to move.
You can specify a directory server object by one of the following values:

- Name of the server object (name)
- A distinguished name  of the NTDS Settings object
- A distinguished name of the server object that represents the directory server
- GUID (objectGUID) of server object under the configuration partition
- GUID (objectGUID) of NTDS settings object under the configuration partition

You can also set the *Identity* parameter to a directory server object variable such as `$<localDirectoryServerObject>`, or you can pass an object through the pipeline to the *Identity* parameter.
For example, you can use the **Get-ADDomainController** cmdlet to get a directory server object and then pass that object through the pipeline to the **Move-ADDirectoryServer** cmdlet.

The *Site* parameter specifies the new site for the directory server.
You can identify a site by its distinguished name or GUID.

## EXAMPLES

### Example 1: Move a domain controller to an existing site
```
PS C:\> Move-ADDirectoryServer -Identity "USER01-DC2" -Site "Branch-Office-Site"
```

This command moves the domain controller USER01-DC2 to the site Branch-Office-Site.

### Example 2: Move read-only domain controllers to an existing site
```
PS C:\> Get-ADDomainController -Filter "IsReadOnly -eq `$True" | Move-ADDirectoryServer -Site "RODC-Site-Name"
```

This command moves all Read-Only domain controllers to the site RODC-Site-Name.

## PARAMETERS

### -AuthType
Specifies the authentication method to use.
The acceptable values for this parameter are:

- Negotiate or 0
- Basic or 1

The default authentication method is Negotiate.

A Secure Sockets Layer (SSL) connection is required for the Basic authentication method.

```yaml
Type: ADAuthType
Parameter Sets: (All)
Aliases:
Accepted values: Negotiate, Basic

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

### -Credential
Specifies the user account credentials to use to perform this task.
The default credentials are the credentials of the currently logged on user unless the cmdlet is run from an Active Directory module for Windows PowerShell provider drive.
If the cmdlet is run from such a provider drive, the account associated with the drive is the default.

To specify this parameter, you can type a user name, such as User1 or Domain01\User01 or you can specify a **PSCredential** object.
If you specify a user name for this parameter, the cmdlet prompts for a password.

You can also create a **PSCredential** object by using a script or by using the **Get-Credential** cmdlet.
You can then set the *Credential* parameter to the **PSCredential** object.

If the acting credentials do not have directory-level permission to perform the task, Active Directory module for Windows PowerShell returns a terminating error.

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

### -Identity
Specifies an Active Directory server object by providing one of the following values.
The identifier in parentheses is the Lightweight Directory Access Protocol (LDAP) display name for the attribute.

- Name of the server object (name)

For Active Directory Lightweight Directory Services (AD LDS) instances the syntax is of a name is `<computer-name>$<instance-name>`

Note: When you type this value in Windows PowerShell, you must use the backtick (\`) as an escape character for the dollar sign ($), for example, *asia-w7-vm4`$instance1*.

For other Active Directory instances, use the value of the name property.

- A distinguished Name of the NTDS Settings object
- A distinguished name of the server object that represents the directory server
- GUID (objectGUID) of server object under the configuration partition
- GUID (objectGUID) of NTDS settings object under the configuration partition

The cmdlet searches the default naming context or partition to find the object.
If two or more objects are found, the cmdlet returns a non-terminating error.

This parameter can also get this object through the pipeline or you can set this parameter to an object instance.

```yaml
Type: ADDirectoryServer
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Server
Specifies the Active Directory Domain Services instance to connect to, by providing one of the following values for a corresponding domain name or directory server.
The service may be any of the following:  Active Directory Lightweight Domain Services, Active Directory Domain Services or Active Directory snapshot instance.

Specify the Active Directory Domain Services instance in one of the following ways:

Domain name values:

- Fully qualified domain name
- NetBIOS name

Directory server values:

- Fully qualified directory server name
- NetBIOS name
- Fully qualified directory server name and port

The default value for this parameter is determined by one of the following methods in the order that they are listed:

- By using the *Server* value from objects passed through the pipeline
- By using the server information associated with the Active Directory Domain Services Windows PowerShell provider drive, when the cmdlet runs in that drive
- By using the domain of the computer running Windows PowerShell

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

### -Site
Specifies the new site for the directory server.
You can identify the site by one of the following property values.
Note: The identifier in parentheses is the LDAP display name for the attribute.
The acceptable values for this parameter are:

- A distinguished name
- A GUID (objectGUID)
- A name (name)

```yaml
Type: ADReplicationSite
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
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

### None or Microsoft.ActiveDirectory.Management.ADDirectoryServer
A directory server object is received by the *Identity* parameter.

## OUTPUTS

### None

## NOTES
* This cmdlet does not work with an Active Directory snapshot.
* This cmdlet does not work with a read-only domain controller.


## RELATED LINKS

[Move-ADDirectoryServerOperationMasterRole](./Move-ADDirectoryServerOperationMasterRole.md)

[AD DS Administration Cmdlets in Windows PowerShell](./activedirectory.md)

