---
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
online version: https://learn.microsoft.com/powershell/module/activedirectory/move-adobject?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Move-ADObject

## SYNOPSIS
Moves an Active Directory object or a container of objects to a different container or domain.

## SYNTAX

```
Move-ADObject [-WhatIf] [-Confirm] [-AuthType <ADAuthType>] [-Credential <PSCredential>] [-Identity] <ADObject>
 [-Partition <String>] [-PassThru] [-Server <String>] [-TargetPath] <String> [-TargetServer <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Move-ADObject** cmdlet moves an object or a container of objects from one container to another or from one domain to another within the same forest.

The Identity parameter specifies the Active Directory object or container to move.
You can identify an object or container by its distinguished name (DN) or GUID.
You can also set the Identity parameter to an object variable such as $\<localObject\>, or you can pass an object through the pipeline to the Identity parameter.
For example, you can use the Get-ADObject cmdlet to retrieve an object and then pass the object through the pipeline to the Move-ADObject cmdlet.
You can also use the Get-ADGroup, Get-ADUser, Get-ADComputer, Get-ADServiceAccount, Get-ADOrganizationalUnit and Get-ADFineGrainedPasswordPolicy cmdlets to get an object that you can pass through the pipeline to this cmdlet.

The TargetPath parameter must be specified.
This parameter identifies the new location for the object or container.

The cmdlet also moves the password when a user or computer object is moved across domains within a forest.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Move-ADObject -Identity "OU=ManagedGroups,DC=Fabrikam,DC=Com" -TargetPath "OU=Managed,DC=Fabrikam,DC=Com"
```

Description

-----------

Moves the Organizational Unit 'ManagedGroups' to a new location.
The OU 'ManagedGroups' must NOT be protected from accidental deletion for the successful move.

### -------------------------- EXAMPLE 2 --------------------------
```
C:\PS>Move-ADObject "8d0bcc44-c826-4dd8-af5c-2c69960fbd47" -TargetPath "OU=Managed,DC=Fabrikam,DC=Com"
```

Description

-----------

Moves the object identified by the specified GUID to the new location.

### -------------------------- EXAMPLE 3 --------------------------
```
C:\PS>Move-ADObject "8d0bcc44-c826-4dd8-af5c-2c69960fbd47" -TargetPath "1c2ea8a8-c2b7-4a87-8190-0e8a166aee16"
```

Description

-----------

Moves an object to a new location.
Both the object and the target path are specified using GUIDs.

### -------------------------- EXAMPLE 4 --------------------------
```
C:\PS>Move-ADObject -Identity "CN=Peter Bankov,OU=Accounting,DC=Fabrikam,DC=com" -TargetPath "OU=Accounting,DC=Europe,DC=Fabrikam,DC=com" -TargetServer "server01.europe.fabrikam.com"
```

Description

-----------

Moves an object with DistinguishedName 'CN=Peter Bankov,OU=Accounting,DC=Fabrikam,DC=com' to a different domain.

### -------------------------- EXAMPLE 5 --------------------------
```
C:\PS>Move-ADObject -Identity "CN=AccountLeads,DC=AppNC" -TargetPath "OU=AccountDeptOU,DC=AppNC" -server "FABRIKAM-SRV1:60000"
```

Description

-----------

Moves an object to a new location within an LDS instance.

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
Specifies an Active Directory object by providing one of the following property values.
The identifier in parentheses is the LDAP display name for the attribute.

Distinguished Name

Example: CN=saradavis,OU=users,OU=asia,DC=corp,DC=contoso,DC=com

GUID (objectGUID)

Example: 599c3d2e-f72d-4d20-8a88-030d99495f20

The cmdlet searches the default naming context or partition to find the object.
If two or more objects are found, the cmdlet returns a non-terminating error.

This parameter can also get this object through the pipeline or you can set this parameter to an object instance.

Derived types, such as the following are also accepted:

Microsoft.ActiveDirectory.Management.ADGroup

Microsoft.ActiveDirectory.Management.ADUser

Microsoft.ActiveDirectory.Management.ADComputer

Microsoft.ActiveDirectory.Management.ADServiceAccount

Microsoft.ActiveDirectory.Management.ADFineGrainedPasswordPolicy

Microsoft.ActiveDirectory.Management.ADDomain

This example shows how to set this parameter to an ADObject object instance named "ADObjectInstance".

-Identity   $ADObjectInstance

```yaml
Type: ADObject
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Partition
Specifies the distinguished name of an Active Directory partition.
The distinguished name must be one of the naming contexts on the current directory server.
The cmdlet searches this partition to find the object defined by the Identity parameter.

The following two examples show how to specify a value for this parameter.

-Partition "CN=Configuration,DC=EUROPE,DC=TEST,DC=CONTOSO,DC=COM"

-Partition "CN=Schema,CN=Configuration,DC=EUROPE,DC=TEST,DC=CONTOSO,DC=COM"

In many cases, a default value will be used for the Partition parameter if no value is specified. 
The rules for determining the default value are given below. 
Note that rules listed first are evaluated first and once a default value can be determined, no further rules will be evaluated.

In AD DS environments, a default value for Partition will be set in the following cases:  - If the Identity parameter is set to a distinguished name, the default value of Partition is automatically generated from this distinguished name.

- If running cmdlets from an Active Directory provider drive, the default value of Partition is automatically generated from the current path in the drive.
- If none of the previous cases apply, the default value of Partition will be set to the default partition or naming context of the target domain.

In AD LDS environments, a default value for Partition will be set in the following cases:

- If the Identity parameter is set to a distinguished name, the default value of Partition is automatically generated from this distinguished name.
- If running cmdlets from an Active Directory provider drive, the default value of Partition is automatically generated from the current path in the drive.
- If the target AD LDS instance has a default naming context, the default value of Partition will be set to the default naming context.  To specify a default naming context for an AD LDS environment, set the msDS-defaultNamingContext property of the Active Directory directory service agent (DSA) object (nTDSDSA) for the AD LDS instance.
- If none of the previous cases apply, the Partition parameter will not take any default value.

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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetPath
Specifies the new location for the object.
This location must be the path to a container or organizational unit.

The following example shows how to specify a target path by providing the distinguished name.

-TargetPath "ou=sales,dc=corp,dc=contoso,dc=com"

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

### -TargetServer
Specifies the Active Directory instance to use by providing the following value for a corresponding domain name or directory server.

Note: A cross domain move requires a FQDN server name.

Domain name values:

Fully qualified domain name (FQDN)

Examples: contoso.com

Directory server values:

Fully qualified directory server name

Example: server01.europe.contoso.com

Fully qualified directory server name and port

Example: server01.europe.contoso.com:3268

The following example shows how to specify a target server by specifying the fully-qualified directory server name.

-TargetServer "server01.europe.contoso.com"

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.ActiveDirectory.Management.AObject
An Active Directory object is received by the Identity parameter.
Derived types, such as the following are also accepted:

Microsoft.ActiveDirectory.Management.ADGroup

Microsoft.ActiveDirectory.Management.ADUser

Microsoft.ActiveDirectory.Management.ADComputer

Microsoft.ActiveDirectory.Management.ADServiceAccount

Microsoft.ActiveDirectory.Management.ADOrganizationalUnit

Microsoft.ActiveDirectory.Management.ADFineGrainedPasswordPolicy

## OUTPUTS

### None

## NOTES
* This cmdlet does not work with an Active Directory Snapshot.

  This cmdlet does not work with a read-only domain controller.

## RELATED LINKS

[Get-ADObject](./Get-ADObject.md)

[New-ADObject](./New-ADObject.md)

[Remove-ADObject](./Remove-ADObject.md)

[Rename-ADObject](./Rename-ADObject.md)

[Restore-ADObject](./Restore-ADObject.md)

[Set-ADObject](./Set-ADObject.md)

