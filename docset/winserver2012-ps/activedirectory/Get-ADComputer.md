---
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
ms.assetid: F3EECD4C-C26D-4423-B699-6F369AB8FFF6
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: kenwith
author: kenwith
---

# Get-ADComputer

## SYNOPSIS
Gets one or more Active Directory computers.

## SYNTAX

### Filter (Default)
```
Get-ADComputer [-AuthType <ADAuthType>] [-Credential <PSCredential>] -Filter <String> [-Properties <String[]>]
 [-ResultPageSize <Int32>] [-ResultSetSize <Int32>] [-SearchBase <String>] [-SearchScope <ADSearchScope>]
 [-Server <String>] [<CommonParameters>]
```

### Identity
```
Get-ADComputer [-AuthType <ADAuthType>] [-Credential <PSCredential>] [-Identity] <ADComputer>
 [-Partition <String>] [-Properties <String[]>] [-Server <String>] [<CommonParameters>]
```

### LdapFilter
```
Get-ADComputer [-AuthType <ADAuthType>] [-Credential <PSCredential>] -LDAPFilter <String>
 [-Properties <String[]>] [-ResultPageSize <Int32>] [-ResultSetSize <Int32>] [-SearchBase <String>]
 [-SearchScope <ADSearchScope>] [-Server <String>] [<CommonParameters>]
```

## DESCRIPTION
The Get-ADComputer cmdlet gets a computer or performs a search to retrieve multiple computers.

The Identity parameter specifies the Active Directory computer to retrieve.
You can identify a computer by its distinguished name (DN), GUID, security identifier (SID) or Security Accounts Manager (SAM) account name.
You can also set the parameter to a computer object variable, such as $\<localComputerObject\> or pass a computer object through the pipeline to the Identity parameter.

To search for and retrieve more than one computer, use the Filter or LDAPFilter parameters.
The Filter parameter uses the PowerShell Expression Language to write query strings for Active Directory.
PowerShell Expression Language syntax provides rich type conversion support for value types received by the Filter parameter.
For more information about the Filter parameter syntax, see about_ActiveDirectory_Filter.
If you have existing LDAP query strings, you can use the LDAPFilter parameter.

This cmdlet retrieves a default set of computer object properties.
To retrieve additional properties use the Properties parameter.
For more information about the how to determine the properties for computer objects, see the Properties parameter description.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Get-ADComputer "Fabrikam-SRV1" -Properties *

AccountExpirationDate              :
accountExpires                     : 9223372036854775807
AccountLockoutTime                 :
AccountNotDelegated                : False
AllowReversiblePasswordEncryption  : False
BadLogonCount                      :
CannotChangePassword               : False
CanonicalName                      : Fabrikam.com/Computers/fabrikam-srv1
Certificates                       : {}
CN                                 : fabrikam-srv1
codePage                           : 0
countryCode                        : 0
Created                            : 3/16/2009 4:15:00 PM
createTimeStamp                    : 3/16/2009 4:15:00 PM
Deleted                            :
Description                        :
DisplayName                        :
DistinguishedName                  : CN=fabrikam-srv1,CN=Computers,DC=Fabrikam,
DC=com
DNSHostName                        :
DoesNotRequirePreAuth              : False
dSCorePropagationData              : {3/16/2009 4:21:51 PM, 12/31/1600 4:00:01
PM}
Enabled                            : True
HomedirRequired                    : False
HomePage                           :
instanceType                       : 0
IPv4Address                        :
IPv6Address                        :
isCriticalSystemObject             : False
isDeleted                          :
LastBadPasswordAttempt             :
LastKnownParent                    :
LastLogonDate                      :
localPolicyFlags                   : 0
Location                           : NA/HQ/Building A
LockedOut                          : False
ManagedBy                          : CN=SQL Administrator 01,OU=UserAccounts,OU
=Managed,DC=Fabrikam,DC=com
MemberOf                           : {}
MNSLogonAccount                    : False
Modified                           : 3/16/2009 4:23:01 PM
modifyTimeStamp                    : 3/16/2009 4:23:01 PM
msDS-User-Account-Control-Computed : 0
Name                               : fabrikam-srv1
nTSecurityDescriptor               : System.DirectoryServices.ActiveDirectorySe
curity
ObjectCategory                     : CN=Computer,CN=Schema,CN=Configuration,DC=
Fabrikam,DC=com
ObjectClass                        : computer
ObjectGUID                         : 828306a3-8ccd-410e-9537-e6616662c0b0
objectSid                          : S-1-5-21-41432690-3719764436-1984117282-11
30
OperatingSystem                    :
OperatingSystemHotfix              :
OperatingSystemServicePack         :
OperatingSystemVersion             :
PasswordExpired                    : False
PasswordLastSet                    :
PasswordNeverExpires               : False
PasswordNotRequired                : False
PrimaryGroup                       : CN=Domain Computers,CN=Users,DC=Fabrikam,D
C=com
primaryGroupID                     : 515
ProtectedFromAccidentalDeletion    : False
pwdLastSet                         : 0
SamAccountName                     : fabrikam-srv1$
sAMAccountType                     : 805306369
sDRightsEffective                  : 0
ServiceAccount                     : {}
servicePrincipalName               : {MSOLAPSVC.3/FABRIKAM-SRV1.FABRIKAM.COM:an
alyze, MSSQLSVC/FABRIKAM-SRV1.FABRIKAM.COM
:1456}
ServicePrincipalNames              : {MSOLAPSVC.3/FABRIKAM-SRV1.FABRIKAM.COM:an
alyze, MSSQLSVC/FABRIKAM-SRV1.FABRIKAM.COM
:1456}
SID                                : S-1-5-21-41432690-3719764436-1984117282-11
30
SIDHistory                         : {}
TrustedForDelegation               : False
TrustedToAuthForDelegation         : False
UseDESKeyOnly                      : False
userAccountControl                 : 4096
userCertificate                    : {}
UserPrincipalName                  :
uSNChanged                         : 36024
uSNCreated                         : 35966
whenChanged                        : 3/16/2009 4:23:01 PM
whenCreated                        : 3/16/2009 4:15:00 PM
```

Description

-----------

Get a specific computer showing all the properties.

### -------------------------- EXAMPLE 2 --------------------------
```
C:\PS>Get-ADComputer -Filter 'Name -like "Fabrikam*"' -Properties IPv4Address | FT Name,DNSHostName,IPv4Address -A

name          dnshostname                ipv4address
----          -----------                -----------
FABRIKAM-SRV1 FABRIKAM-SRV1.Fabrikam.com 10.194.99.181
FABRIKAM-SRV2 FABRIKAM-SRV2.Fabrikam.com 10.194.100.37
```

Description

-----------

Get all the computers with a name starting by a particular string and showing the name, dns hostname and IPv4 address.

### -------------------------- EXAMPLE 3 --------------------------
```
C:\PS>$d = [DateTime]::Today.AddDays(-90); Get-ADComputer -Filter 'PasswordLastSet -ge $d' -Properties PasswordLastSet | FT Name,PasswordLastSet

Name                                                        PasswordLastSet
----                                                        ---------------
FABRIKAM-SRV4                                               3/12/2009 6:40:37 PM
FABRIKAM-SRV5                                               3/12/2009 7:05:45 PM
```

Description

-----------

Get all the computers that have changed their password in the last 90 days.

### -------------------------- EXAMPLE 4 --------------------------
```
C:\PS>Get-ADComputer -LDAPFilter "(name=*laptop*)" -SearchBase "CN=Computers,DC=Fabrikam,DC=com"

name
----
saradavi-laptop
jeffpr-laptop
```

Description

-----------

Get the computer accounts in the location: "CN=Computers,DC=Fabrikam,DC=com" that are listed as laptops (using an LDAPFilter)

### -------------------------- EXAMPLE 5 --------------------------
```
C:\PS>Get-ADComputer -Filter *
```

Description

-----------

Get all computer accounts.

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

Get-ADUser -Filter {EmailAddress -like "*"}

Get-ADUser -Filter {mail -like "*"}

-or-

Get-ADObject -Filter {(mail -like "*") -and (ObjectClass -eq "user")}

Note: PowerShell wildcards other than "*", such as "?" are not supported by the Filter syntax.

To get all users objects that have surname of Smith and that have an e-mail attribute, use one of the following commands:

Get-ADUser -filter {(EmailAddress -like "*") -and (Surname  -eq "smith")}

-or-

Get-ADUser -filter {(mail -eq "*") -and (sn -eq "Smith")}

To get all user objects who have not logged on since January 1, 2007, use the following commands:

$logonDate = New-Object System.DateTime(2007, 1, 1)

Get-ADUser  -filter { lastLogon -le $logonDate  }

To get all groups that have a group category of Security and a group scope of Global, use one of the following commands:

Get-ADGroup  -filter {GroupCategory  -eq "Security"  -and GroupScope -eq "Global"}

-or-

Get-ADGroup -filter {GroupType -band 0x80000000}

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
Specifies an Active Directory computer object by providing one of the following property values.
The identifier in parentheses is the LDAP display name for the attribute.

Distinguished Name

Example: CN=SaraDavisDesktop,CN=Europe,CN=Users,DC=corp,DC=contoso,DC=com

GUID  (objectGUID)

Example: 599c3d2e-f72d-4d20-8a88-030d99495f20

Security Identifier (objectSid)

Example: S-1-5-21-3165297888-301567370-576410423-1103

Security Accounts Manager Account Name (sAMAccountName)

Example: SaraDavisDesktop

The cmdlet searches the default naming context or partition to find the object.
If the identifier given is a DN, the partition to search will be computed from that DN.
If two or more objects are found, the cmdlet returns a non-terminating error.

This parameter can also get this object through the pipeline or you can set this parameter to a computer object instance.

This example shows how to set the parameter to a distinguished name.

-Identity  "CN=saraDavisDesktop,CN=Europe,CN=Users,DC=corp,DC=contoso,DC=com"

This example shows how to set this parameter to a computer object instance named "computerInstance".

-Identity   $computerInstance

```yaml
Type: ADComputer
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

### None or Microsoft.ActiveDirectory.Management.ADComputer
A computer object is received by the Identity parameter.

## OUTPUTS

### Microsoft.ActiveDirectory.Management.ADComputer
Returns one or more computer objects.

This Get-ADComputer cmdlet returns a default set of ADComputer property values.
To retrieve additional ADComputer properties, use the Properties parameter of this cmdlet.

To view the properties for an ADComputer object, see the following examples.
To run these examples, replace \<computer\> with a computer identifier such as the SAM account name of your local computer.

To get a list of the default set of properties of an ADComputer object, use the following command:

Get-ADComputer \<computer\>| Get-Member

To get a list of all the properties of an ADComputer object, use the following command:

Get-ADComputer \<computer\> -Properties ALL | Get-Member

## NOTES
* This cmdlet does not work with AD LDS with its default schema.  By default AD LDS schema does not have a computer class, but if the schema is extended to include it, this cmdlet will work with LDS.

## RELATED LINKS

[Add-ADComputerServiceAccount](./Add-ADComputerServiceAccount.md)

[Get-ADComputerServiceAccount](./Get-ADComputerServiceAccount.md)

[New-ADComputer](./New-ADComputer.md)

[Remove-ADComputer](./Remove-ADComputer.md)

[Remove-ADComputerServiceAccount](./Remove-ADComputerServiceAccount.md)

[Set-ADComputer](./Set-ADComputer.md)

