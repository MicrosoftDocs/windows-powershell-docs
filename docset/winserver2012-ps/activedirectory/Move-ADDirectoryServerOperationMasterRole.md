---
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
ms.assetid: C779A4F5-0BB8-4E7B-B91C-FC44E2DBE160
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Move-ADDirectoryServerOperationMasterRole

## SYNOPSIS
Moves operation master roles to an Active Directory directory server.

## SYNTAX

```
Move-ADDirectoryServerOperationMasterRole [-WhatIf] [-Confirm] [-AuthType <ADAuthType>]
 [-Credential <PSCredential>] [-Force] [-Identity] <ADDirectoryServer>
 [-OperationMasterRole] <ADOperationMasterRole[]> [-PassThru] [-Server <String>] [<CommonParameters>]
```

## DESCRIPTION
The Move-ADDirectoryServerOperationMasterRole cmdlet moves one or more operation master roles to a directory server.
You can move operation master roles to a directory server in a different domain if the credentials are the same in both domains.

The Identity parameter specifies the directory server that receives the roles.
You can specify a directory server object by one of the following values:

Name of the server object (name)

Distinguished Name (DN) of the NTDS Settings object

Distinguished Name (DN) of the server object that represents the directory server

GUID (objectGUID) of server object under the configuration partition

GUID (objectGUID) of NTDS settings object under the configuration partition

For AD LDS instances the syntax for the server object name is \<computer-name\>$\<instance-name\>.
The following is an example of this syntax:

asia-w7-vm4$instance1

When you type this value in Windows PowerShell, you must use the backtick (\`) as an escape character for the dollar sign ($).
Therefore, for this example, you would type the following:

asia-w7-vm4\`$instance1

You can also set the parameter to a directory server object variable, such as $\<localDirectoryServerObject\>.

The Move-ADDirectoryServerOperationMasterRole cmdlet provides two options for moving operation master roles:

1. Role transfer, which involves transferring roles to be moved by running the cmdlet using the Identity parameter to specify the current role holder and the OperationMasterRole parameter to specify the roles for transfer.
   This is the recommended option.

   Operation roles include PDCEmulator, RIDMaster, InfrastructureMaster, SchemaMaster, or DomainNamingMaster.
   To specify more than one role, use a comma-separated list.

2. Role seizure, which involves seizing roles you previously attempted to transfer by running the cmdlet a second time using the same parameters as the transfer operation, and adding the Force parameter.
   The Force parameter must be used as a switch to indicate that seizure (instead of transfer) of operation master roles is being performed.
   This operation still attempts graceful transfer first, then seizes if transfer is not possible.

Unlike using Ntdsutil.exe to move operation master roles, the Move-ADDirectoryServerOperationMasterRole cmdlet can be remotely executed from any domain joined computer where the Active Directory PowerShell administration module is installed and available for use.
This can make the process of moving roles simpler and easier to centrally administer as each of the two command operations required can be run remotely and do not have to be locally executed at each of the corresponding role holders involved in the movement of the roles (i.e.
role transfer only allowed at the old role holder, role seizure only allowed at the new role holder).

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Move-ADDirectoryServerOperationMasterRole "FABRIKAM-DC1" PDCEmulator
```

Description

-----------

Move the PDC Emulator role to the Domain Controller "FABRIKAM-DC1".

### -------------------------- EXAMPLE 2 --------------------------
```
C:\PS>Move-ADDirectoryServerOperationMasterRole -Identity "FABRIKAM-DC2" -OperationMasterRole PDCEmulator,SchemaMaster
```

Description

-----------

Move the PDC Emulator and Schema Master roles to the Domain Controller "FABRIKAM-DC2".

### -------------------------- EXAMPLE 3 --------------------------
```
C:\PS>Move-ADDirectoryServerOperationMasterRole Fabrikam-DC`$instance1 -OperationMasterRole schemaMaster -server Fabrikam-DC:50000
```

Description

-----------

Move the schema master FSMO owner to the AD LDS instance "instance1' on the server "Fabrikam-DC".

### -------------------------- EXAMPLE 4 --------------------------
```
C:\PS>Move-ADDirectoryServerOperationMasterRole -Identity FABRIKAM-DC1 -OperationMasterRole RIDMaster,InfrastructureMaster,DomainNamingMaster -Force
```

Description

-----------

Seizes the specified roles (RID master, infrastructure master, domain naming master).

### -------------------------- EXAMPLE 5 --------------------------
```
PS C:\>$server = Get-ADDomainController -Identity "TK5-CORP-DC-10.fabrikam.com"


PS C:\>Move-ADDirectoryServerOperationMasterRole -Identity $server -OperationMasterRole SchemaMaster,DomainNamingMaster,PDCEmulator,RIDMaster,InfrastructureMaster
```

Description

-----------

Transfers the flexible single master operations (FSMO) role to the specified domain controller.
When using the fully qualified domain name (FQDN) to identify the domain controller, the Get-ADDomainController cmdlet must be used first as a preliminary step.
There is a known issue where the Move-ADDirectoryServerOperationMasterRole cmdlet fails when an FQDN is specified directly as the value of the **-Identity** parameter.

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

### -Force
This parameter is used for seize operations on domain controllers with the flexible single master operations (FSMO) role.

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

### -OperationMasterRole
Specifies one or more operation master roles to move to the specified directory server in Active Directory Domain Services.
Possible values for this parameter include:

PDCEmulator or 0

RIDMaster or 1

InfrastructureMaster or 2

SchemaMaster or 3

DomainNamingMaster or 4

To specify multiple operation master roles, use a comma-separated list.

The following example shows how to specify this parameter so that the SchemaMaster and DomainNamingMaster roles are moved.

-OperationMasterRole SchemaMaster, 4

```yaml
Type: ADOperationMasterRole[]
Parameter Sets: (All)
Aliases: 
Accepted values: PDCEmulator, RIDMaster, InfrastructureMaster, SchemaMaster, DomainNamingMaster

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Returns the new or modified object.
By default (i.e.
if -PassThru is not specified), this cmdlet does not generate any output.

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
Default value: See notes
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

### Microsoft.ActiveDirectory.Management.ADDirectoryServer
A directory server object is received by the Identity parameter.

## OUTPUTS

### None or Microsoft.ActiveDirectory.Management.ADDirectoryServer
Returns the modified directory server object when the PassThru parameter is specified.
By default, this cmdlet does not generate any output.

## NOTES
* This cmdlet does not work with an Active Directory Snapshot.

  This cmdlet does not work with a read-only domain controller.

## RELATED LINKS

[Move-ADDirectoryServer](./Move-ADDirectoryServer.md)

