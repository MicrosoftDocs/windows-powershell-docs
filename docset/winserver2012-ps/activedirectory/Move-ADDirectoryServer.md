---
author: Kateyanne
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
manager: dansimp
Module Name: ActiveDirectory
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/activedirectory/move-addirectoryserver?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
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
The Move-ADDirectoryServer cmdlet moves a directory server in Active Directory to a new site within the same domain.

The Identity parameter specifies the directory server to move.
You can specify a directory server object by one of the following values:

Name of the server object (name)

Distinguished Name (DN) of the NTDS Settings object

Distinguished Name (DN) of the server object that represents the directory server

GUID (objectGUID) of server object under the configuration partition

GUID (objectGUID) of NTDS settings object under the configuration partition

You can also set the Identity parameter to a directory server object variable such as $\<localDirectoryServerObject\>, or you can pass an object through the pipeline to the Identity parameter.
For example, you can use the Get-ADDomainController to get a directory server object and then pass that object through the pipeline to the Move-ADDirectoryServer cmdlet.

The Site parameter specifies the new site for the directory server.
You can identify a site by its distinguished name (DN) or GUID.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Move-ADDirectoryServer -Identity "FABRIKAM-DC2" -Site "Branch-Office-Site"
```

Description

-----------

Move the domain controller "FABRIKAM-DC2" to the site "Branch-Office-Site".

### -------------------------- EXAMPLE 2 --------------------------
```
C:\PS>Get-ADDomainController -Filter "IsReadOnly -eq `$true" | Move-ADDirectoryServer -site "RODC-Site-Name"
```

Description

-----------

Move all Read Only Domain Controllers to the site "RODC-Site-Name".

## PARAMETERS

### -AuthType
Specifies the authentication method to use.
Possible values for this parameter include:

Negotiate or 0

Basic or 1

The default authentication method is Negotiate.

A Secure Sockets Layer (SSL) connection is required for the Basic authentication method.

The following example shows how to set this parameter to Basic.

-AuthType Basic

```yaml
Type: ADAuthType
Parameter Sets: (All)
Aliases: 
Accepted values: Negotiate, Basic

Required: False
Position: Named
Default value: Microsoft.ActiveDirectory.Management.AuthType.Negotiate
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
The default credentials are the credentials of the currently logged on user unless the cmdlet is run from an Active Directory PowerShell provider drive.
If the cmdlet is run from such a provider drive, the account associated with the drive is the default.

To specify this parameter, you can type a user name, such as "User1" or "Domain01\User01" or you can specify a PSCredential object.
If you specify a user name for this parameter, the cmdlet prompts for a password.

You can also create a PSCredential object by using a script or by using the Get-Credential cmdlet.
You can then set the Credential parameter to the PSCredential object The following example shows how to create credentials.

$AdminCredentials = Get-Credential "Domain01\User01"

The following shows how to set the Credential parameter to these credentials.

-Credential $AdminCredentials

If the acting credentials do not have directory-level permission to perform the task, Active Directory PowerShell returns a terminating error.

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
The identifier in parentheses is the LDAP display name for the attribute.

Name of the server object (name)

For AD LDS instances the syntax is of a name is \<computer-name\>$\<instance-name\>

Example: asia-w7-vm4$instance1

Note: When you type this value in Windows PowerShell, you must use the backtick (\`) as an escape character for the dollar sign ($).
Therefore, for the previous example you would type the following: asia-w7-vm4\`$instance1

For other Active Directory instances, use the value of the name property

Example: corp-DC01

Distinguished Name of the NTDS Settings object

Example: CN=NTDS Settings,CN=CORP-DC12,CN=Servers,CN=NA-CAN-BC,CN=Sites,CN=Configuration,DC=corp,DC=contoso

Distinguished Name of the server object that represents the directory server

Example: CN=CORP-DC12,CN=Servers,CN=NA-CAN-QBC,CN=Sites,CN=Configuration,DC=corp,DC=contoso,DC=com

GUID (objectGUID) of server object under the configuration partition

Example: 599c3d2e-f72d-4d20-8a88-030d99495f20

GUID (objectGUID) of NTDS settings object under the configuration partition

Example: 768c44de-f72d-66e0-8a88-0523ca495f20

The cmdlet searches the default naming context or partition to find the object.
If two or more objects are found, the cmdlet returns a non-terminating error.

This parameter can also get this object through the pipeline or you can set this parameter to an object instance.

This example shows how to set the parameter to a distinguished name.

-Identity "CN=CORP-DC12,CN=Servers,CN=NA-CAN-QBC,CN=Sites,CN=Configuration,DC=corp,DC=contoso,DC=com"

This example shows how to set this parameter to a directory server object instance named "directoryServerInstance".

-Identity   $directoryServerInstance

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
The service may be any of the following:  Active Directory Lightweight Domain Services, Active Directory Domain Services or Active Directory Snapshot instance.

Domain name values:

Fully qualified domain name

Examples: corp.contoso.com

NetBIOS name

Example: CORP

Directory server values:

Fully qualified directory server name

Example: corp-DC12.corp.contoso.com

NetBIOS name

Example: corp-DC12

Fully qualified directory server name and port

Example: corp-DC12.corp.contoso.com:3268

The default value for the Server parameter is determined by one of the following methods in the order that they are listed:

-By using Server value from objects passed through the pipeline.

-By using the server information associated with the Active Directory PowerShell provider drive, when running under that drive.

-By using the domain of the computer running Powershell.

The following example shows how to specify a full qualified domain name as the parameter value.

-Server "corp.contoso.com"

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

Distinguished name (DN)

Example: CN= NA-CAN-QBC,CN=Sites,CN=Configuration,DC=corp,DC=contoso,DC=com

GUID (ObjectGUID)

Example: 599c3d2e-f72d-4d20-8a88-030d99495f20

Name (name)

Example: NA-CAN-QBC

The following example shows how use this parameter to specify a site object by using the site name.

-Site  "NA-CAN-QBC"

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None or Microsoft.ActiveDirectory.Management.ADDirectoryServer
A directory server object is received b y the Identity parameter.

## OUTPUTS

### None

## NOTES
* This cmdlet does not work with an Active Directory Snapshot.

  This cmdlet does not work with a read-only domain controller.

## RELATED LINKS

[Move-ADDirectoryServerOperationMasterRole](./Move-ADDirectoryServerOperationMasterRole.md)

