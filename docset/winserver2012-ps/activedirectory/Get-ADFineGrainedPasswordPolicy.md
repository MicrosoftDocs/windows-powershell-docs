---
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
online version: https://docs.microsoft.com/powershell/module/activedirectory/get-adfinegrainedpasswordpolicy?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-ADFineGrainedPasswordPolicy

## SYNOPSIS
Gets one or more Active Directory fine grained password policies.

## SYNTAX

### Filter (Default)
```
Get-ADFineGrainedPasswordPolicy [-AuthType <ADAuthType>] [-Credential <PSCredential>] -Filter <String>
 [-Properties <String[]>] [-ResultPageSize <Int32>] [-ResultSetSize <Int32>] [-SearchBase <String>]
 [-SearchScope <ADSearchScope>] [-Server <String>] [<CommonParameters>]
```

### Identity
```
Get-ADFineGrainedPasswordPolicy [-AuthType <ADAuthType>] [-Credential <PSCredential>]
 [-Identity] <ADFineGrainedPasswordPolicy> [-Properties <String[]>] [-Server <String>] [<CommonParameters>]
```

### LdapFilter
```
Get-ADFineGrainedPasswordPolicy [-AuthType <ADAuthType>] [-Credential <PSCredential>] -LDAPFilter <String>
 [-Properties <String[]>] [-ResultPageSize <Int32>] [-ResultSetSize <Int32>] [-SearchBase <String>]
 [-SearchScope <ADSearchScope>] [-Server <String>] [<CommonParameters>]
```

## DESCRIPTION
The Get-ADFineGrainedPasswordPolicy cmdlet gets a fine grained password policy or performs a search to retrieve multiple fine grained password policies.

The Identity parameter specifies the Active Directory fine grained password policy to get.
You can identify a fine grained password policy by its distinguished name (DN), GUID or name.
You can also set the parameter to a fine grained password policy object variable, such as $\<localFineGrainedPasswordPolicyObject\> or pass a fine grained password policy object through the pipeline to the Identity parameter.

To search for and retrieve more than one fine grained password policies, use the Filter or LDAPFilter parameters.
The Filter parameter uses the PowerShell Expression Language to write query strings for Active Directory.
PowerShell Expression Language syntax provides rich type conversion support for value types received by the Filter parameter.
For more information about the Filter parameter syntax, see about_ActiveDirectory_Filter.
If you have existing LDAP query strings, you can use the LDAPFilter parameter.

This cmdlet retrieves a default set of fine grained password policy object properties.
To retrieve additional properties use the Properties parameter.
For more information about the how to determine the properties for FineGrainedPasswordPolicy objects, see the Properties parameter description.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Get-ADFineGrainedPasswordPolicy -Filter "Name -like '*'" | ft Name, Precedence,MaxPasswordAge,MinPasswordLength -A


Name           Precedence MaxPasswordAge MinPasswordLength
----           ---------- -------------- -----------------
DomainUsersPSO        500 60.00:00:00                    8
SvcAccPSO             100 30.00:00:00                   20
AdminsPSO             200 15.00:00:00                   10
DlgtdAdminsPSO        300 20.00:00:00                   10
```

Description

-----------

### -------------------------- EXAMPLE 2 --------------------------
```
C:\PS>Get-ADFineGrainedPasswordPolicy AdminsPSO


Name                        : AdminsPSO
ComplexityEnabled           : True
LockoutThreshold            : 0
ReversibleEncryptionEnabled : True
LockoutDuration             : 00:30:00
LockoutObservationWindow    : 00:30:00
MinPasswordLength           : 10
Precedence                  : 200
ObjectGUID                  : ba1061f0-c947-4018-a399-6ad8897d26e3
ObjectClass                 : msDS-PasswordSettings
PasswordHistoryCount        : 24
MinPasswordAge              : 1.00:00:00
MaxPasswordAge              : 15.00:00:00
AppliesTo                   : {}
DistinguishedName           : CN=AdminsPSO,CN=Password Settings Container,CN=System,DC=FABRIKAM,DC=COM
```

Description

-----------

Get the Fine Grained Password Policy named 'AdminsPSO'.

### -------------------------- EXAMPLE 3 --------------------------
```
C:\PS>Get-ADFineGrainedPasswordPolicy 'CN=DlgtdAdminsPSO,CN=Password Settings Container,CN=System,DC=FABRIKAM,DC=COM' -Properties *


msDS-LockoutDuration                     : -18000000000
msDS-PasswordSettingsPrecedence          : 300
ObjectCategory                           : CN=ms-DS-Password-Settings,CN=Schema,CN=Configuration,DC=FABRIKAM,DC=COM
DistinguishedName                        : CN=DlgtdAdminsPSO,CN=Password Settings Container,CN=System,DC=FABRIKAM,DC=COM
ExpireOn                                 :
msDS-MinimumPasswordAge                  : -864000000000
dSCorePropagationData                    : {12/31/1600 4:00:00 PM}
msDS-LockoutThreshold                    : 0
Description                              : The Delegated Administrators Password Policy
LockoutThreshold                         : 0
instanceType                             : 4
msDS-PasswordComplexityEnabled           : True
MaxPasswordAge                           : 20.00:00:00
whenCreated                              : 8/15/2008 12:47:43 AM
Name                                     : DlgtdAdminsPSO
ObjectClass                              : msDS-PasswordSettings
ReversibleEncryptionEnabled              : True
msDS-PasswordReversibleEncryptionEnabled : True
Dynamic                                  : False
LockoutDuration                          : 00:30:00
msDS-PSOAppliesTo                        : {CN=Kim Abercrombie,OU=Finance,OU=UserAccounts,DC=FABRIKAM,DC=COM, CN=Bob Kelly,OU=AsiaPacific,OU=Sales,OU=UserAccounts,DC=FABRIKAM,DC=COM}
DisplayName                              : Delegated Administrators PSO
uSNCreated                               : 16395
Modified                                 : 8/20/2008 12:21:15 AM
MinPasswordAge                           : 1.00:00:00
ProtectedFromAccidentalDeletion          : False
Created                                  : 8/15/2008 12:47:43 AM
sDRightsEffective                        : 15
ComplexityEnabled                        : True
PasswordHistoryCount                     : 24
msDS-MaximumPasswordAge                  : -17280000000000
MinPasswordLength                        : 10
Precedence                               : 300
ObjectGUID                               : 75cf8c7a-9c93-4e81-b611-851803372cb2
msDS-MinimumPasswordLength               : 10
Deleted                                  :
Orphaned                                 : False
CN                                       : DlgtdAdminsPSO
LastKnownParent                          :
CanonicalName                            : FABRIKAM.COM/System/Password Settings Container/DlgtdAdminsPSO
modifyTimeStamp                          : 8/20/2008 12:21:15 AM
msDS-LockoutObservationWindow            : -18000000000
LockoutObservationWindow                 : 00:30:00
whenChanged                              : 8/20/2008 12:21:15 AM
createTimeStamp                          : 8/15/2008 12:47:43 AM
msDS-PasswordHistoryLength               : 24
nTSecurityDescriptor                     : System.DirectoryServices.ActiveDirectorySecurity
AppliesTo                                : {CN=JeffPrice,OU=Finance,OU=UserAccounts,DC=FABRIKAM,DC=COM, CN=GlenJohn,OU=AsiaPacific,OU=Sales,OU=UserAccounts,DC=FABRIKAM,DC=COM}
uSNChanged                               : 72719
```

Description

-----------

Get all the properties for the Fine Grained Password Policy with DistinguishedName 'CN=DlgtdAdminsPSO,CN=Password Settings Container,CN=System,DC=FABRIKAM,DC=COM'.

### -------------------------- EXAMPLE 4 --------------------------
```
C:\PS>Get-ADFineGrainedPasswordPolicy -Filter "name -like '*admin*'"

AppliesTo                   : {CN=GlenJohn,CN=Users,DC=Fabrikam,DC=com, CN=JeffPrice,CN=Users,DC=Fabrikam,DC=com, CN=Administrator,CN=Users,DC=Fabrikam,DC=com}
ComplexityEnabled           : True
DistinguishedName           : CN=DlgtdAdminsPSO,CN=Password Settings Container,CN=System,DC=Fabrikam,DC=com
LockoutDuration             : 00:30:00
LockoutObservationWindow    : 00:30:00
LockoutThreshold            : 0
MaxPasswordAge              : 42.00:00:00
MinPasswordAge              : 1.00:00:00
MinPasswordLength           : 7
Name                        : DlgtdAdminsPSO
ObjectClass                 : msDS-PasswordSettings
ObjectGUID                  : b7de4e6e-c291-4ce6-bb47-6bf8f807df53
PasswordHistoryCount        : 24
Precedence                  : 100
ReversibleEncryptionEnabled : True
```

Description

-----------

Get all the Fine Grained Password Policy object that have a name that begins with admin.

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
Specifies an Active Directory fine-grained password policy object by providing one of the following property values.
The identifier in parentheses is the LDAP display name for the attribute.

Distinguished Name (distinguishedName)

Example: CN=Strict Password Policy,CN=Password Settings Container,CN=System,DC=corp,DC=contoso,DC=com

GUID (objectGUID)

Example: 599c3d2e-f72d-4d20-8a88-030d99495f20

Name (name)

Example: PasswordPolicyLevel1

The cmdlet searches the default naming context or partition to find the object.
If two or more objects are found, the cmdlet returns a non-terminating error.

This parameter can also get this object through the pipeline or you can set this parameter to a fine-grained password policy object instance.

This example shows how to set the parameter to a distinguished name.

-Identity "CN=Strict Password Policy,CN=Password Settings Container,CN=System,DC=corp,DC=contoso,DC=com"

This example shows how to set this parameter to a fine-grained password policy object instance named "fineGrainedPasswordPolicyInstance".

-Identity $fineGrainedPasswordPolicyInstance

```yaml
Type: ADFineGrainedPasswordPolicy
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

### None or Microsoft.ActiveDirectory.Management.ADFineGrainedPasswordPolicy
A fine grained password policy is received by the Identity parameter.

## OUTPUTS

### Microsoft.ActiveDirectory.Management.ADFineGrainedPasswordPolicy
Returns one or more fine grained password policy objects.

This cmdlet returns a default set of ADFineGrainedPasswordPolicy property values.
To retrieve additional ADFineGrainedPasswordPolicy properties, use the Properties parameter.

To view the properties for an ADFineGrainedPasswordPolicy object, see the following examples.
To run these examples, replace \<fine grained password policy\> with a fine grained password policy identifier such as the name of your local fine grained password policy.

To get a list of the default set of properties of an ADFineGrainedPasswordPolicy object, use the following command:

Get-ADFineGrainedPasswordPolicy \<fine grained password policy\>| Get-Member

To get a list of all the properties of an ADFineGrainedPasswordPolicy object, use the following command:

Get-ADFineGrainedPasswordPolicy \<fine grained password policy\> -Properties * | Get-Member

## NOTES
* This cmdlet does not work with AD LDS.

  This cmdlet does not work when targeting a snapshot using the Server parameter.

## RELATED LINKS

[Add-ADFineGrainedPasswordPolicySubject](./Add-ADFineGrainedPasswordPolicySubject.md)

[New-ADFineGrainedPasswordPolicy](./New-ADFineGrainedPasswordPolicy.md)

[Remove-ADFineGrainedPasswordPolicy](./Remove-ADFineGrainedPasswordPolicy.md)

[Remove-ADFineGrainedPasswordPolicySubject](./Remove-ADFineGrainedPasswordPolicySubject.md)

[Set-ADFineGrainedPasswordPolicy](./Set-ADFineGrainedPasswordPolicy.md)

