---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/activedirectory/get-adfinegrainedpasswordpolicy?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ADFineGrainedPasswordPolicy
---

# Get-ADFineGrainedPasswordPolicy

## SYNOPSIS
Gets one or more Active Directory fine-grained password policies.

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
The **Get-ADFineGrainedPasswordPolicy** cmdlet gets a fine-grained password policy or performs a search to retrieve multiple fine-grained password policies.

The *Identity* parameter specifies the Active Directory fine-grained password policy to get.
You can identify a fine-grained password policy by its distinguished name, GUID or name.
You can also set the parameter to a fine-grained password policy object variable, such as `$<localFineGrainedPasswordPolicyObject>` or pass a fine-grained password policy object through the pipeline operator to the *Identity* parameter.

To search for and retrieve more than one fine-grained password policies, use the *Filter* or *LDAPFilter* parameters.
The *Filter* parameter uses Windows PowerShell Expression Language to write query strings for Active Directory.
Windows PowerShell Expression Language syntax provides rich type conversion support for value types received by the *Filter* parameter.
For more information about the *Filter* parameter syntax, type `Get-Help about_ActiveDirectory_Filter`.
If you have existing Lightweight Directory Access Protocol (LDAP) query strings, you can use the *LDAPFilter* parameter.

This cmdlet retrieves a default set of fine-grained password policy object properties.
To retrieve additional properties use the *Properties* parameter.
For more information about the how to determine the properties for **FineGrainedPasswordPolicy** objects, see the *Properties* parameter description.

## EXAMPLES

### Example 1: Get a fine-grained policy using a name
```
PS C:\> Get-ADFineGrainedPasswordPolicy -Identity AdminsPSO
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
DistinguishedName           : CN=AdminsPSO,CN=Password Settings Container,CN=System,DC=USER01,DC=COM
```

This command gets the fine-grained password policy named AdminsPSO.

### Example 2: Get all properties for a fine-grained password policy using a distinguished name
```
PS C:\> Get-ADFineGrainedPasswordPolicy -Identity 'CN=DlgtdAdminsPSO,CN=Password Settings Container,CN=System,DC=USER01,DC=COM' -Properties *
msDS-LockoutDuration                     : -18000000000
msDS-PasswordSettingsPrecedence          : 300
ObjectCategory                           : CN=ms-DS-Password-Settings,CN=Schema,CN=Configuration,DC=USER01,DC=COM
DistinguishedName                        : CN=DlgtdAdminsPSO,CN=Password Settings Container,CN=System,DC=USER01,DC=COM
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
msDS-PSOAppliesTo                        : {CN=Kim Abercrombie,OU=Finance,OU=UserAccounts,DC=USER01,DC=COM, CN=Bob Kelly,OU=AsiaPacific,OU=Sales,OU=UserAccounts,DC=USER01,DC=COM}
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
CanonicalName                            : USER01.COM/System/Password Settings Container/DlgtdAdminsPSO
modifyTimeStamp                          : 8/20/2008 12:21:15 AM
msDS-LockoutObservationWindow            : -18000000000
LockoutObservationWindow                 : 00:30:00
whenChanged                              : 8/20/2008 12:21:15 AM
createTimeStamp                          : 8/15/2008 12:47:43 AM
msDS-PasswordHistoryLength               : 24
nTSecurityDescriptor                     : System.DirectoryServices.ActiveDirectorySecurity
AppliesTo                                : {CN=JeffPrice,OU=Finance,OU=UserAccounts,DC=USER01,DC=COM, CN=GlenJohn,OU=AsiaPacific,OU=Sales,OU=UserAccounts,DC=USER01,DC=COM}
uSNChanged                               : 72719
```

This command gets all the properties for the fine-grained password policy with DistinguishedName CN=DlgtdAdminsPSO,CN=Password Settings Container,CN=System,DC=USER01,DC=COM.

### Example 3: Get all fine-grained password policy objects using a filter
```
PS C:\> Get-ADFineGrainedPasswordPolicy -Filter "name -like '*admin*'"
AppliesTo                   : {CN=GlenJohn,CN=Users,DC=USER01,DC=com, CN=JeffPrice,CN=Users,DC=USER01,DC=com, CN=Administrator,CN=Users,DC=USER01,DC=com}
ComplexityEnabled           : True
DistinguishedName           : CN=DlgtdAdminsPSO,CN=Password Settings Container,CN=System,DC=USER01,DC=com
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

This command gets all the fine-grained password policy objects that have a name that begins with admin.

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

### -Filter
Specifies a query string that retrieves Active Directory objects.
This string uses the PowerShell Expression Language syntax.
The PowerShell Expression Language syntax provides rich type-conversion support for value types received by the *Filter* parameter.
The syntax uses an in-order representation, which means that the operator is placed between the operand and the value.
For more information about the *Filter* parameter, type `Get-Help about_ActiveDirectory_Filter`.

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

For a list of supported types for \<value\>, type `Get-Help about_ActiveDirectory_ObjectModel`.

Note: PowerShell wildcards other than *, such as ?, are not supported by the *Filter* syntax.

Note: To query using LDAP query strings, use the *LDAPFilter* parameter.

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
The acceptable values for this parameter are:

- A distinguished name
- A GUID (objectGUID)

The cmdlet searches the default naming context or partition to find the object.
If two or more objects are found, the cmdlet returns a non-terminating error.

This parameter can also get this object through the pipeline or you can set this parameter to a fine-grained password policy object instance.

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
The *Filter* parameter syntax supports the same functionality as the LDAP syntax.
For more information, see the *Filter* parameter description or type `Get-Help about_ActiveDirectory_Filter`.

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

To retrieve properties and display them for an object, you can use the Get-* cmdlet associated with the object and pass the output to the **Get-Member** cmdlet.

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

### -ResultSetSize
Specifies the maximum number of objects to return for an Active Directory Domain Services query.
If you want to receive all of the objects, set this parameter to $Null (null value).
You can use Ctrl+C to stop the query and return of objects.

The default is $Null.

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

When you run a cmdlet outside of an Active Directory provider drive against an Active Directory Domain Services target, the default value of this parameter is the default naming context of the target domain.

When you run a cmdlet outside of an Active Directory provider drive against an Active Directory Lightweight Directory Services (AD LDS) target, the default value is the default naming context of the target LDS instance if one has been specified by setting the **msDS-defaultNamingContext** property of the Active Directory directory service agent (DSA) object (**nTDSDSA**) for the AD LDS instance.
If no default naming context is specified for the target AD LDS instance, then this parameter has no default value.

When the value of the *SearchBase* parameter is set to an empty string and you are connected to a global catalog port, all partitions are searched.
If the value of the *SearchBase* parameter is set to an empty string and you are not connected to a global catalog port, an error is thrown.

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
The acceptable values for this parameter are:

- Base or 0
- OneLevel or 1
- Subtree or 2

A Base query searches only the current path or object.
A OneLevel query searches the immediate children of that path or object.
A Subtree query searches the current path or object and all children of that path or object.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None or Microsoft.ActiveDirectory.Management.ADFineGrainedPasswordPolicy
A fine-grained password policy is received by the *Identity* parameter.

## OUTPUTS

### Microsoft.ActiveDirectory.Management.ADFineGrainedPasswordPolicy
This cmdlet returns one or more fine-grained password policy objects.

This cmdlet returns a default set of **ADFineGrainedPasswordPolicy** property values.
To retrieve additional **ADFineGrainedPasswordPolicy** properties, use the *Properties* parameter.

To view the properties for an **ADFineGrainedPasswordPolicy** object, see the following examples.
To run these examples, replace \<fine grained password policy\> with a fine-grained password policy identifier such as the name of your local fine-grained password policy.

To get a list of the default set of properties of an **ADFineGrainedPasswordPolicy** object, use the following command:

`Get-ADFineGrainedPasswordPolicy`\<fine grained password policy\>`| Get-Member`

To get a list of all the properties of an **ADFineGrainedPasswordPolicy** object, use the following command:

`Get-ADFineGrainedPasswordPolicy`\<fine grained password policy\>`-Properties * | Get-Member`

## NOTES
* This cmdlet does not work with AD LDS.
* This cmdlet does not work when targeting a snapshot using the *Server* parameter.

## RELATED LINKS

[Add-ADFineGrainedPasswordPolicySubject](./Add-ADFineGrainedPasswordPolicySubject.md)

[New-ADFineGrainedPasswordPolicy](./New-ADFineGrainedPasswordPolicy.md)

[Remove-ADFineGrainedPasswordPolicy](./Remove-ADFineGrainedPasswordPolicy.md)

[Remove-ADFineGrainedPasswordPolicySubject](./Remove-ADFineGrainedPasswordPolicySubject.md)

[Set-ADFineGrainedPasswordPolicy](./Set-ADFineGrainedPasswordPolicy.md)

[AD DS Administration Cmdlets in Windows PowerShell](./activedirectory.md)

