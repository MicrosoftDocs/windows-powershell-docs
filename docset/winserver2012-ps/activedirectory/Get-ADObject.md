---
author: Kateyanne
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
manager: dansimp
Module Name: ActiveDirectory
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/activedirectory/get-adobject?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-ADObject

## SYNOPSIS
Gets one or more Active Directory objects.

## SYNTAX

### Filter (Default)
```
Get-ADObject [-AuthType <ADAuthType>] [-Credential <PSCredential>] -Filter <String> [-IncludeDeletedObjects]
 [-Properties <String[]>] [-ResultPageSize <Int32>] [-ResultSetSize <Int32>] [-SearchBase <String>]
 [-SearchScope <ADSearchScope>] [-Server <String>] [<CommonParameters>]
```

### Identity
```
Get-ADObject [-AuthType <ADAuthType>] [-Credential <PSCredential>] [-Identity] <ADObject>
 [-IncludeDeletedObjects] [-Partition <String>] [-Properties <String[]>] [-Server <String>]
 [<CommonParameters>]
```

### LdapFilter
```
Get-ADObject [-AuthType <ADAuthType>] [-Credential <PSCredential>] [-IncludeDeletedObjects]
 -LDAPFilter <String> [-Properties <String[]>] [-ResultPageSize <Int32>] [-ResultSetSize <Int32>]
 [-SearchBase <String>] [-SearchScope <ADSearchScope>] [-Server <String>] [<CommonParameters>]
```

## DESCRIPTION
The Get-ADObject cmdlet gets an Active Directory object or performs a search to retrieve multiple objects.

The Identity parameter specifies the Active Directory object to get.
You can identify the object to get by its distinguished name (DN) or GUID.
You can also set the parameter to an Active Directory object variable, such as $\<localADObject\> or pass an object through the pipeline to the Identity parameter.

To search for and retrieve more than one object, use the Filter or LDAPFilter parameters.
The Filter parameter uses the PowerShell Expression Language to write query strings for Active Directory.
PowerShell Expression Language syntax provides rich type conversion support for value types received by the Filter parameter.
For more information about the Filter parameter syntax, see about_ActiveDirectory_Filter.
If you have existing LDAP query strings, you can use the LDAPFilter parameter.

This cmdlet gets a default set of Active Directory object properties.
To get additional properties use the Properties parameter.
For more information about the how to determine the properties for computer objects, see the Properties parameter description.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Get-ADObject -LDAPFilter "(objectClass=site)" -SearchBase 'CN=Configuration,DC=Fabrikam,DC=Com' -Properties CanonicalName | FT Name,CanonicalName -A


Name CanonicalName
---- -------------
HQ   FABRIKAM.COM/Configuration/Sites/HQ
BO1  FABRIKAM.COM/Configuration/Sites/BO1
BO2  FABRIKAM.COM/Configuration/Sites/BO2
BO3  FABRIKAM.COM/Configuration/Sites/BO3
```

Description

-----------

Displays a list of sites for Fabrikam using the LDAP filter syntax.

### -------------------------- EXAMPLE 2 --------------------------
```
C:\PS>Get-ADObject -Filter 'ObjectClass -eq "site"' -SearchBase 'CN=Configuration,DC=Fabrikam,DC=Com' -Properties siteObjectBL | foreach {$_.siteObjectBL}


CN=192.167.1.0/26,CN=Subnets,CN=Sites,CN=Configuration,DC=FABRIKAM,DC=COM
CN=192.166.1.0/26,CN=Subnets,CN=Sites,CN=Configuration,DC=FABRIKAM,DC=COM
CN=192.168.1.0/26,CN=Subnets,CN=Sites,CN=Configuration,DC=FABRIKAM,DC=COM
CN=192.165.1.0/26,CN=Subnets,CN=Sites,CN=Configuration,DC=FABRIKAM,DC=COM
CN=192.164.1.0/26,CN=Subnets,CN=Sites,CN=Configuration,DC=FABRIKAM,DC=COM
CN=192.163.1.0/26,CN=Subnets,CN=Sites,CN=Configuration,DC=FABRIKAM,DC=COM
CN=192.162.1.0/26,CN=Subnets,CN=Sites,CN=Configuration,DC=FABRIKAM,DC=COM
CN=192.161.1.0/26,CN=Subnets,CN=Sites,CN=Configuration,DC=FABRIKAM,DC=COM
CN=192.160.1.0/26,CN=Subnets,CN=Sites,CN=Configuration,DC=FABRIKAM,DC=COM
CN=192.159.1.0/26,CN=Subnets,CN=Sites,CN=Configuration,DC=FABRIKAM,DC=COM
CN=192.158.1.0/26,CN=Subnets,CN=Sites,CN=Configuration,DC=FABRIKAM,DC=COM
CN=192.157.1.0/26,CN=Subnets,CN=Sites,CN=Configuration,DC=FABRIKAM,DC=COM
```

Description

-----------

Gets the Site objects from the Configuration Naming Context and then enumerates through the list outputting 'siteObjectBL'.

### -------------------------- EXAMPLE 3 --------------------------
```
C:\PS>$changeDate = New-Object DateTime(2008, 11, 18, 1, 40, 02); Get-ADObject -Filter 'whenChanged -gt $changeDate' -IncludeDeletedObjects
```

Description

-----------

Gets all the objects, including the deleted ones, whose 'whenChanged' attribute is greater than the specified date.
Note that both deleted and non-deleted (and non-recycled) objects matching the filter will be returned.

### -------------------------- EXAMPLE 4 --------------------------
```
C:\PS>$changeDate = New-Object DateTime(2008, 11, 18, 1, 40, 02)
Get-ADObject -Filter 'whenChanged -gt $changeDate -and isDeleted -eq $true -and -not (isRecycled -eq $true) -and name -ne "Deleted Objects"' -IncludeDeletedObjects

ObjectGUID        : 98118958-91c7-437d-8ada-ba0b66db823b
Deleted           : True
DistinguishedName : CN=Andrew Ma\0ADEL:98118958-91c7-437d-8ada-ba0b66db823b,CN=Deleted Objects,DC=FABRIKAM,DC=COM
Name              : Andrew Ma
DEL:98118958-91c7-437d-8ada-ba0b66db823b
ObjectClass       : user
```

Description

-----------

Gets all the deleted objects, whose 'whenChanged' attribute is greater than the specified date.
The clause 'name -ne "Deleted Objects"' makes sure that the Deleted Objects Container is not returned.
This will only return objects which can be restored

### -------------------------- EXAMPLE 5 --------------------------
```
C:\PS>$changeDate = New-Object DateTime(2008, 11, 18, 1, 40, 02)
Get-ADObject -Filter 'whenChanged -gt $changeDate -and isDeleted -eq $true -and -not (isRecycled -eq $true) -and lastKnownParent -eq "OU=Accounting,DC=Fabrikam,DC=com"' -IncludeDeletedObjects

ObjectGUID        : 12d53e7f-aaf7-4790-b41a-da19044504db
Deleted           : True
DistinguishedName : CN=Craig Dewar\0ADEL:12d53e7f-aaf7-4790-b41a-da19044504db,CN=Deleted Objects,DC=Fabrikam,DC=com
Name              : Craig Dewar
DEL:12d53e7f-aaf7-4790-b41a-da19044504db
ObjectClass       : user
```

Description

-----------

Gets all the deleted objects whose 'whenChanged' attribute is greater then the specified date AND at the time of deletion were the children of the specified Organizational Unit.

### -------------------------- EXAMPLE 6 --------------------------
```
C:\PS>Get-ADObject -Identity "DC=AppNC" -server "FABRIKAM-SRV1:60000"

ObjectGUID                    DistinguishedName             Name                          ObjectClass
----------                    -----------------             ----                          -----------
62b2e185-9322-4980-9c93-cf... DC=AppNC                      AppNC                         domainDNS
```

Description

-----------

Gets the information of the domainDNS object of an LDS instance

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

### -Filter
Specifies a query string that retrieves Active Directory objects.
This string uses the PowerShell Expression Language syntax.
The PowerShell Expression Language syntax provides rich type-conversion support for value types received by the Filter parameter.
The syntax uses an in-order representation, which means that the operator is placed between the operand and the value.
For more information about the Filter parameter, see about_ActiveDirectory_Filter.

Syntax:

The following syntax uses Backus-Naur form to show how to use the PowerShell Expression Language for this parameter.

\<filter\>  ::= "{" \<FilterComponentList\> "}"

\<FilterComponentList\> ::= \<FilterComponent\> | \<FilterComponent\> \<JoinOperator\> \<FilterComponent\> | \<NotOperator\>  \<FilterComponent\>

\<FilterComponent\> ::= \<attr\> \<FilterOperator\> \<value\> | "(" \<FilterComponent\> ")"

\<FilterOperator\> ::= "-eq" | "-le" | "-ge" | "-ne" | "-lt" | "-gt"| "-approx" | "-bor" | "-band" | "-recursivematch" | "-like" | "-notlike"

\<JoinOperator\> ::= "-and" | "-or"

\<NotOperator\> ::= "-not"

\<attr\> ::= \<PropertyName\> | \<LDAPDisplayName of the attribute\>

\<value\>::= \<compare this value with an \<attr\> by using the specified \<FilterOperator\>\>

For a list of supported types for \<value\>, see about_ActiveDirectory_ObjectModel.

Examples:

The following examples show how to use this syntax with Active Directory cmdlets.

To get all objects of the type specified by the cmdlet, use the asterisk wildcard:

All user objects:

Get-ADUser -Filter *

-or-

All computer objects:

Get-ADComputer -Filter *

To get all user objects that have an e-mail message attribute, use one of the following commands:

Get-ADUser -Filter "EmailAddress -like '*'"

Get-ADUser -Filter "mail -like '*'"

-or-

Get-ADObject -Filter "(mail -like '*') -and (ObjectClass -eq 'user')"

Note: PowerShell wildcards other than "*", such as "?" are not supported by the Filter syntax.

To get all users objects that have surname of Smith and that have an e-mail attribute, use one of the following commands:

Get-ADUser -Filter "(EmailAddress -like '*') -and (Surname -eq 'smith')"

-or-

Get-ADUser -Filter "(mail -eq '*') -and (sn -eq 'Smith')"

To get all user objects who have not logged on since January 1, 2007, use the following commands:

$logonDate = New-Object System.DateTime(2007, 1, 1)

Get-ADUser -Filter "lastLogon -le '$logonDate'"

To get all groups that have a group category of Security and a group scope of Global, use one of the following commands:

Get-ADGroup -Filter "GroupCategory -eq 'Security' -and GroupScope -eq 'Global'"

-or-

Get-ADGroup -Filter "GroupType -band 0x80000000"

Note: To query using LDAP query strings, use the LDAPFilter parameter.

```yaml
Type: String
Parameter Sets: Filter
Aliases: 

Required: True
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
Parameter Sets: Identity
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -IncludeDeletedObjects
Specifies to retrieve deleted objects and the deactivated forward and backward links.
When this parameter is specified, the cmdlet uses the following LDAP controls:

Show Deleted Objects (1.2.840.113556.1.4.417)

Show Deactivated Links (1.2.840.113556.1.4.2065)

Note: If this parameter is not specified, the cmdlet will not return or operate on deleted objects.

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

### -LDAPFilter
Specifies an LDAP query string that is used to filter Active Directory objects.
You can use this parameter to run your existing LDAP queries.
The Filter parameter syntax supports the same functionality as the LDAP syntax.
For more information, see the Filter parameter description and the about_ActiveDirectory_Filter.

The following example shows how to set this parameter to search for all objects in the organizational unit specified by the SearchBase parameter with a name beginning with "sara".

-LDAPFilter "(name=sara*)"  -SearchScope Subtree -SearchBase "DC=NA,DC=fabrikam,DC=com"

```yaml
Type: String
Parameter Sets: LdapFilter
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
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
Parameter Sets: Identity
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Properties
Specifies the properties of the output object to retrieve from the server.
Use this parameter to retrieve properties that are not included in the default set.

Specify properties for this parameter as a comma-separated list of names.
To display all of the attributes that are set on the object, specify * (asterisk).

To specify an individual extended property, use the name of the property.
For properties that are not default or extended properties, you must specify the LDAP display name of the attribute.

To retrieve properties and display them for an object, you can use the Get-* cmdlet associated with the object and pass the output to the Get-Member cmdlet.
The following examples show how to retrieve properties for a group where the Administrator's group is used as the sample group object.

Get-ADGroup -Identity Administrators | Get-Member

To retrieve and display the list of all the properties for an ADGroup object, use the following command:

Get-ADGroup -Identity Administrators -Properties *| Get-Member

The following examples show how to use the Properties parameter to retrieve individual properties as well as the default, extended or complete set of properties.

To retrieve the extended properties "OfficePhone" and "Organization" and the default properties of an ADUser object named "SaraDavis", use the following command:

GetADUser -Identity SaraDavis  -Properties OfficePhone,Organization

To retrieve the properties with LDAP display names of "otherTelephone" and "otherMobile", in addition to the default properties for the same user, use the following command:

GetADUser -Identity SaraDavis  -Properties otherTelephone, otherMobile |Get-Member

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: Property

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResultPageSize
Specifies the number of objects to include in one page for an Active Directory Domain Services query.

The default is 256 objects per page.

The following example shows how to set this parameter.

-ResultPageSize 500

```yaml
Type: Int32
Parameter Sets: Filter, LdapFilter
Aliases: 

Required: False
Position: Named
Default value: 256
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResultSetSize
Specifies the maximum number of objects to return for an Active Directory Domain Services query.
If you want to receive all of the objects, set this parameter to $null (null value).
You can use Ctrl+c to stop the query and return of objects.

The default is $null.

The following example shows how to set this parameter so that you receive all of the returned objects.

-ResultSetSize $null

```yaml
Type: Int32
Parameter Sets: Filter, LdapFilter
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SearchBase
Specifies an Active Directory path to search under.

When you run a cmdlet from an Active Directory provider drive, the default value of this parameter is the current path of the drive.

When you run a cmdlet outside of an Active Directory provider drive against an AD DS target, the default value of this parameter is the default naming context of the target domain.

When you run a cmdlet outside of an Active Directory provider drive against an AD LDS target, the default value is the default naming context of the target LDS instance if one has been specified by setting the msDS-defaultNamingContext property of the Active Directory directory service agent (DSA) object (nTDSDSA) for the AD LDS instance. 
If no default naming context has been specified for the target AD LDS instance, then this parameter has no default value.

The following example shows how to set this parameter to search under an OU.

-SearchBase "ou=mfg,dc=noam,dc=corp,dc=contoso,dc=com"

When the value of the SearchBase parameter is set to an empty string and you are connected to a GC port, all partitions will be searched.
If the value of the SearchBase parameter is set to an empty string and you are not connected to a GC port, an error will be thrown.

The following example shows how to set this parameter to an empty string. 
-SearchBase ""

```yaml
Type: String
Parameter Sets: Filter, LdapFilter
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SearchScope
Specifies the scope of an Active Directory search.
Possible values for this parameter are:

Base or 0

OneLevel or 1

Subtree or 2

A Base query searches only the current path or object.
A OneLevel query searches the immediate children of that path or object.
A Subtree query searches the current path or object and all children of that path or object.

The following example shows how to set this parameter to a subtree search.

-SearchScope Subtree

```yaml
Type: ADSearchScope
Parameter Sets: Filter, LdapFilter
Aliases: 
Accepted values: Base, OneLevel, Subtree

Required: False
Position: Named
Default value: Subtree
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

-By using the domain of the computer running Windows PowerShell.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None or Microsoft.ActiveDirectory.Management.ADObject
An Active Directory object is received by the Identity parameter.

## OUTPUTS

### Microsoft.ActiveDirectory.Management.ADObject
Derived types, such as the following are also accepted:
  Microsoft.ActiveDirectory.Management.ADGroup
  Microsoft.ActiveDirectory.Management.ADUser
  Microsoft.ActiveDirectory.Management.ADComputer
  Microsoft.ActiveDirectory.Management.ADServiceAccount
  Microsoft.ActiveDirectory.Management.ADOrganizationalUnit
  Microsoft.ActiveDirectory.Management.ADFineGrainedPasswordPolicy
  Microsoft.ActiveDirectory.Management.ADDomain
Returns one or more Active Directory objects.

The Get-ADObject cmdlet returns a default set of ADObject property values.
To retrieve additional ADObject properties, use the Properties parameter of the cmdlet.

To view the properties for an ADObject object, see the following examples.
To run these examples, replace \<object\> with an Active Directory object identifier.

To get a list of the default set of properties of an ADObject object, use the following command:

Get-ADObject \<object\>| Get-Member

To get a list of all the properties of an ADObject object, use the following command:

Get-ADObject \<object\> -Properties ALL | Get-Member

## NOTES

## RELATED LINKS

[New-ADObject](./New-ADObject.md)

[Remove-ADObject](./Remove-ADObject.md)

[Set-ADObject](./Set-ADObject.md)

