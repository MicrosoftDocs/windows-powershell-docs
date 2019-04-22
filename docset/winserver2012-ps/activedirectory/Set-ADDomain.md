---
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
ms.assetid: 877E4715-5573-49A9-98D6-04B1444B0273
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: kenwith
author: kenwith
---

# Set-ADDomain

## SYNOPSIS
Modifies an Active Directory domain.

## SYNTAX

### Identity
```
Set-ADDomain [-WhatIf] [-Confirm] [-Add <Hashtable>] [-AllowedDNSSuffixes <Hashtable>] [-AuthType <ADAuthType>]
 [-Clear <String[]>] [-Credential <PSCredential>] [-Identity] <ADDomain>
 [-LastLogonReplicationInterval <TimeSpan>] [-ManagedBy <ADPrincipal>] [-PassThru] [-Remove <Hashtable>]
 [-Replace <Hashtable>] [-Server <String>] [<CommonParameters>]
```

### Instance
```
Set-ADDomain [-WhatIf] [-Confirm] [-AllowedDNSSuffixes <Hashtable>] [-AuthType <ADAuthType>]
 [-Credential <PSCredential>] -Instance <ADDomain> [-LastLogonReplicationInterval <TimeSpan>]
 [-ManagedBy <ADPrincipal>] [-PassThru] [-Server <String>] [<CommonParameters>]
```

## DESCRIPTION
The Set-ADDomain cmdlet modifies the properties of an Active Directory domain.
You can modify commonly used property values by using the cmdlet parameters.
Property values that are not associated with cmdlet parameters can be modified by using the Add, Replace, Clear and Remove parameters.

The Identity parameter specifies the domain to modify.
You can identify a domain by its distinguished name (DN), GUID, security identifier (SID), DNS domain name, or NetBIOS name.
You can also set the Identity parameter to an object variable such as $\<localDomainObject\>, or you can pass an object through the pipeline to the Identity parameter.
For example, you can use the Get-ADDomain cmdlet to retrieve a domain object and then pass the object through the pipeline to the Set-ADDomain cmdlet.

The Instance parameter provides a way to update a domain object by applying the changes made to a copy of the domain object.
When you set the Instance parameter to a copy of an Active Directory domain object that has been modified, the Set-ADDomain cmdlet makes the same changes to the original domain object.
To get a copy of the object to modify, use the Get-ADDomain object.
When you specify the Instance parameter you should not pass the identity parameter. 
For more information about the Instance parameter, see the Instance parameter description.

The following examples show how to modify the ManagedBy property of a domain object by using three methods:

-By specifying the Identity and the ManagedBy parameters

-By passing a domain object through the pipeline and specifying the ManagedBy parameter

-By specifying the Instance parameter.

Method 1: Modify the ManagedBy property for the London domain by using the Identity and ManagedBy parameters.

Set-ADDomain -Identity London -ManagedBy SaraDavis

Method 2: Modify the ManagedBy property for the London domain by passing the London domain through the pipeline and specifying the ManagedBy parameter.

Get-ADDomain London | Set-ADDomain -ManagedBy SaraDavis

Method 3: Modify the ManagedBy property for the London domain by using the Windows PowerShell command line to modify a local instance of the London domain.
Then set the Instance parameter to the local instance.

$domain = Get-ADDomain London

$domain.ManagedBy = SaraDavis

Set-ADDomain -Instance $domain.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Set-ADDomain -Identity FABRIKAM -AllowedDNSSuffixes @{Replace="fabrikam.com","corp.fabrikam.com"}
```

Description

-----------

Sets the value of AllowedDNSSuffixes to {"fabrikam.com","corp.fabrikam.com"} in domain "FABRIKAM".

### -------------------------- EXAMPLE 2 --------------------------
```
C:\PS>Set-ADDomain -Identity FABRIKAM -AllowedDNSSuffixes @{Add="corp.fabrikam.com"}


Adds the value "corp.fabrikam.com" to the AllowedDNSSuffixes in domain "FABRIKAM".
```

Description

-----------

### -------------------------- EXAMPLE 3 --------------------------
```
C:\PS>Set-ADDomain -Identity FABRIKAM -ManagedBy 'CN=Domain Admins,CN=Users,DC=FABRIKAM,DC=COM'
```

Description

-----------

Sets the ManagedBy property in domain "FABRIKAM" to 'CN=Domain Admins,CN=Users,DC=FABRIKAM,DC=COM'.

### -------------------------- EXAMPLE 4 --------------------------
```
C:\PS>Get-ADDomain | Set-ADDomain -LastLogonReplicationInterval "10"
```

Description

-----------

Sets the LastLogonReplicationInterval of the current logged on user domain to "10".

## PARAMETERS

### -Add
Specifies values to add to an object property.
Use this parameter to add one or more values to a property that cannot be modified using a cmdlet parameter.
To modify an object property, you must use the LDAP display name.
You can specify multiple values to a property by specifying a comma-separated list of values and more than one property by separating them using a semicolon..
The format for this parameter is

-Add @{Attribute1LDAPDisplayName=value1, value2, ...;   Attribute2LDAPDisplayName=value1, value2, ...; AttributeNLDAPDisplayName=value1, value2, ...}

For example, if you want to remove the value "555-222-2222" and add the values "555-222-1111" and "555-222-3333" to Phone-Office-Other attribute (LDAP display name 'otherTelephone'), and add the value "555-222-9999" to Phone-Mobile-Other (LDAP display name 'otherMobile'), set the Add and Remove parameters as follows.

-Add @{otherTelephone='555-222-1111', '555-222-3333'; otherMobile='555-222-9999' } -Remove @{otherTelephone='555-222-2222'}

When you use the Add, Remove, Replace and Clear parameters together, the operations will be performed in the following order:

..Remove

..Add

..Replace

```yaml
Type: Hashtable
Parameter Sets: Identity
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllowedDNSSuffixes
Modifies the list of domain name server (DNS) suffixes that are allowed in a domain.
This parameter sets the value of the msDS-AllowedDNSSuffixes attribute of the domainDNS object.
This parameter uses the following syntax to add, remove, replace, or clear DNS suffix values.

To add values:

-AllowedDNSSuffixes @{Add=value1,value2,...}

To remove values:

-AllowedDNSSuffixes @{Remove=value3,value4,...}

To replace values:

-AllowedDNSSuffixes @{Replace=value1,value2,...}

To clear all values:

-AllowedDNSSuffixes $null

You can specify more than one change by using a list separated by semicolons.
For example, use the following syntax to add and remove DNS suffix values:

@{Add=value1,value2,...};@{Remove=value3,value4,...}

The operators will be applied in the following sequence:

..Remove

..Add

..Replace

The following example shows how to add and remove DNS suffixes for a domain.

-AllowedDNSSuffixes@{Add= "corp.contoso.com,contoso.com"};@{Remove="corpnet.contoso.com"}

```yaml
Type: Hashtable
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -Clear
Specifies an array of object properties that will be cleared in the directory.
Use this parameter to clear one or more values of a property that cannot be modified using a cmdlet parameter.
To modify an object property, you must use the LDAP display name.
You can modify more than one property by specifying a comma-separated list.
The format for this parameter is

-Clear Attribute1LDAPDisplayName, Attribute2LDAPDisplayName

For example, if you want to clear the value for the Phone-Office-Other attribute (LDAP display name 'otherTelephone') set the Clear parameter as follows.

-Clear otherTelephone

When you use the Add, Remove, Replace and Clear parameters together, the operations will be performed in the following order:

..Remove

..Add

..Replace

..Clear

```yaml
Type: String[]
Parameter Sets: Identity
Aliases: 

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
Specifies an Active Directory domain object by providing one of the following property values.
The identifier in parentheses is the LDAP display name for the attribute.
All values are for the domainDNS object that represents the domain.

Distinguished Name

Example: DC=redmond,DC=corp,DC=contoso,DC=com

GUID (objectGUID)

Example: 599c3d2e-f72d-4d20-8a88-030d99495f20

Security Identifier (objectSid)

Example: S-1-5-21-3165297888-301567370-

DNS domain name

Example: redmond.corp.contoso.com

NetBIOS domain name

Example: redmond

The cmdlet searches the default naming context or partition to find the object.
If two or more objects are found, the cmdlet returns a non-terminating error.

This parameter can also get this object through the pipeline or you can set this parameter to a domain object instance.

This example shows how to set the parameter to a distinguished name.

-Identity  "DC=redmond,DC=corp,DC=contoso,DC=com"

This example shows how to set this parameter to a domain object instance named "domainInstance".

-Identity   $domainInstance

```yaml
Type: ADDomain
Parameter Sets: Identity
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Instance
Specifies a modified copy of a domain object to use to update the actual Active Directory domain object.
When this parameter is used, any modifications made to the modified copy of the object are also made to the corresponding Active Directory object.
The cmdlet only updates the object properties that have changed.

The Instance parameter can only update domain objects that have been retrieved by using the Get-ADDomain cmdlet.
When you specify the Instance parameter, you cannot specify other parameters that set properties on the object.

The following is an example of how to use the Get-ADDomain cmdlet to retrieve an instance of the ADDomain object.
The object is modified by using the Windows PowerShell command line.
Then the Set-ADDomain cmdlet saves the changes to the Active Directory object.

Step 1: Retrieve a local instance of the object.

$domainInstance = Get-ADDomain -Identity "contosoDomain"

Step 2: Modify one or more properties of the object instance.

$domainInstance.ManagedBy = "saraDavisGroup"

Step3: Save your changes to contosoDomain.

Set-ADDomain -Instance $domainInstance

```yaml
Type: ADDomain
Parameter Sets: Instance
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LastLogonReplicationInterval
Specifies the time, in days, within which the last logon time of an account must be replicated across all domain controllers in the domain.
This parameter sets the LastLogonReplicationInterval property for a domain.
The LDAP display name (ldapDisplayName) for this property is msDS-LogonTimeSyncInterval.
The last logon replication interval must be at least one day.
Setting the last logon replication interval to a low value can significantly increase domain-wide replication.

The following example shows how to set this parameter to 10 days.

-LastLogonReplicationInterval "10"

Note: This value does not apply when the domain mode is set to the value "Windows2000".

```yaml
Type: TimeSpan
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ManagedBy
Specifies the user or group that manages the object by providing one of the following property values.
Note: The identifier in parentheses is the LDAP display name for the property.

Distinguished Name

Example:  CN=SaraDavis,OU=Europe,CN=Users,DC=corp,DC=contoso,DC=com

GUID (objectGUID)

Example: 599c3d2e-f72d-4d20-8a88-030d99495f20

Security Identifier (objectSid)

Example: S-1-5-21-3165297888-301567370-576410423-1103

SAM Account Name (sAMAccountName)

Example: saradavis

This parameter sets the Active Directory attribute with an LDAP Display Name of "managedBy".

The following example shows how to specify this parameter.

-ManagedBy ContosoAdmins

```yaml
Type: ADPrincipal
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

### -Remove
Specifies that the cmdlet remove values of an object property.
Use this parameter to remove one or more values of a property that cannot be modified using a cmdlet parameter.
To remove an object property, you must use the LDAP display name.
You can remove more than one property by specifying a semicolon-separated list.
The format for this parameter is

-Remove @{Attribute1LDAPDisplayName=value\[\];   Attribute2LDAPDisplayName=value\[\]}

For example, if you want to add the values blue and green and remove the value pink from a property with a LDAP display name of FavColors, set the Add and Remove parameters as follows.

-Add @{FavColors=Blue,Green} -Remove {FavColors=Pink}

When you use the Add, Remove, Replace and Clear parameters together, the parameters will be applied in the following sequence:

..Remove

..Add

..Replace

..Clear

```yaml
Type: Hashtable
Parameter Sets: Identity
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Replace
Specifies values for an object property that will replace the current values.
Use this parameter to replace one or more values of a property that cannot be modified using a cmdlet parameter.
To modify an object property, you must use the LDAP display name.
You can modify more than one property by specifying a comma-separated list.
The format for this parameter is

-Replace @{Attribute1LDAPDisplayName=value\[\],   Attribute2LDAPDisplayName=value\[\]}

For example, if you want to replace the value "555-222-2222" with the values "555-222-1111" for Phone-Office-Other attribute (LDAP display name 'otherTelephone') set the Replace parameter as follows.

-Replace @{otherTelephone='555-222-2222', '555-222-1111'}

When you use the Add, Remove, Replace  and Clear parameters together, the operations will be performed in the following order:

..Remove

..Add

..Replace

..Clear

```yaml
Type: Hashtable
Parameter Sets: Identity
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

### None or Microsoft.ActiveDirectory.Management.ADDomain
A domain object is received by the Identity parameter.

A domain object that was retrieved by using the Get-ADDomain cmdlet and then modified is received by the Instance parameter.

## OUTPUTS

### None or Microsoft.ActiveDirectory.Management.ADDomain
Returns the modified domain object when the PassThru parameter is specified.
By default, this cmdlet does not generate any output.

## NOTES
* This cmdlet does not work with AD LDS.

  This cmdlet does not work with an Active Directory Snapshot.

  This cmdlet does not work with a read-only domain controller.

## RELATED LINKS

[Get-ADDomain](./Get-ADDomain.md)

