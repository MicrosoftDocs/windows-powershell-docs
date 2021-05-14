---
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
online version: https://docs.microsoft.com/powershell/module/activedirectory/get-adresourcepropertylist?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-ADResourcePropertyList

## SYNOPSIS
Retrieves resource property lists from Active Directory.

## SYNTAX

### Filter (Default)
```
Get-ADResourcePropertyList [-AuthType <ADAuthType>] [-Credential <PSCredential>] -Filter <String>
 [-Properties <String[]>] [-ResultPageSize <Int32>] [-ResultSetSize <Int32>] [-Server <String>]
 [<CommonParameters>]
```

### Identity
```
Get-ADResourcePropertyList [-AuthType <ADAuthType>] [-Credential <PSCredential>]
 [-Identity] <ADResourcePropertyList> [-Properties <String[]>] [-Server <String>] [<CommonParameters>]
```

### LdapFilter
```
Get-ADResourcePropertyList [-AuthType <ADAuthType>] [-Credential <PSCredential>] -LDAPFilter <String>
 [-Properties <String[]>] [-ResultPageSize <Int32>] [-ResultSetSize <Int32>] [-Server <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The Get-ADResourcePropertyList cmdlet retrieves resource property lists from Active Directory.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Get-ADResourcePropertyList -Filter *
```

Description

-----------

Retrieves a list of all resource property lists.

### -------------------------- EXAMPLE 2 --------------------------
```
C:\PS>Get-ADResourcePropertyList -Filter "Members -eq 'Country'"
```

Description

-----------

Retrieves all resource property lists that has the resource property "Country" in the list.

### -------------------------- EXAMPLE 3 --------------------------
```
C:\PS>Get-ADResourcePropertyList "Global Resource Property List"
```

Description

-----------

Retrieves the global resource property list.

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

Example:  CN=Global Resource Property List,CN=Resource Property Lists,CN=Claims Configuration,CN=Services,CN=Configuration,DC=corp,DC=contoso,DC=com

GUID (objectGUID)

Example: 599c3d2e-f72d-4d20-8a88-030d99495f20

This parameter can also get this object through the pipeline or you can set this parameter to an object instance.

This example shows how to set this parameter to a user object instance named "ADObjectInstance".

-Identity   $ADObjectInstance

```yaml
Type: ADResourcePropertyList
Parameter Sets: Identity
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None or Microsoft.ActiveDirectory.Management.ADResourcePropertyList

## OUTPUTS

### Microsoft.ActiveDirectory.Management.ADResourcePropertyList

## NOTES
* This cmdlet does not work with an Active Directory Snapshot.

## RELATED LINKS

