---
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
ms.assetid: A01E908C-F344-4072-B720-4A0F523018B2
manager: dansimp
online version: 
schema: 2.0.0
---

# Set-ADUser

## SYNOPSIS
Modifies an Active Directory user.

## SYNTAX

### Identity
```
Set-ADUser [-WhatIf] [-Confirm] [-AccountExpirationDate <DateTime>] [-AccountNotDelegated <Boolean>]
 [-Add <Hashtable>] [-AllowReversiblePasswordEncryption <Boolean>] [-AuthType <ADAuthType>]
 [-CannotChangePassword <Boolean>] [-Certificates <Hashtable>] [-ChangePasswordAtLogon <Boolean>]
 [-City <String>] [-Clear <String[]>] [-Company <String>] [-CompoundIdentitySupported <Boolean>]
 [-Country <String>] [-Credential <PSCredential>] [-Department <String>] [-Description <String>]
 [-DisplayName <String>] [-Division <String>] [-EmailAddress <String>] [-EmployeeID <String>]
 [-EmployeeNumber <String>] [-Enabled <Boolean>] [-Fax <String>] [-GivenName <String>]
 [-HomeDirectory <String>] [-HomeDrive <String>] [-HomePage <String>] [-HomePhone <String>]
 [-Identity] <ADUser> [-Initials <String>] [-KerberosEncryptionType <ADKerberosEncryptionType>]
 [-LogonWorkstations <String>] [-Manager <ADUser>] [-MobilePhone <String>] [-Office <String>]
 [-OfficePhone <String>] [-Organization <String>] [-OtherName <String>] [-Partition <String>] [-PassThru]
 [-PasswordNeverExpires <Boolean>] [-PasswordNotRequired <Boolean>] [-POBox <String>] [-PostalCode <String>]
 [-PrincipalsAllowedToDelegateToAccount <ADPrincipal[]>] [-ProfilePath <String>] [-Remove <Hashtable>]
 [-Replace <Hashtable>] [-SamAccountName <String>] [-ScriptPath <String>] [-Server <String>]
 [-ServicePrincipalNames <Hashtable>] [-SmartcardLogonRequired <Boolean>] [-State <String>]
 [-StreetAddress <String>] [-Surname <String>] [-Title <String>] [-TrustedForDelegation <Boolean>]
 [-UserPrincipalName <String>] [<CommonParameters>]
```

### Instance
```
Set-ADUser [-WhatIf] [-Confirm] [-AuthType <ADAuthType>] [-Credential <PSCredential>] -Instance <ADUser>
 [-PassThru] [-SamAccountName <String>] [-Server <String>] [<CommonParameters>]
```

## DESCRIPTION
The Set-ADUser cmdlet modifies the properties of an Active Directory user.
You can modify commonly used property values by using the cmdlet parameters.
Property values that are not associated with cmdlet parameters can be modified by using the Add, Replace, Clear and Remove parameters.

The Identity parameter specifies the Active Directory user to modify.
You can identify a user by its distinguished name (DN), GUID, security identifier (SID) or Security Accounts Manager (SAM) account name.
You can also set the Identity parameter to an object variable such as $\<localUserObject\>, or you can pass an object through the pipeline to the Identity parameter.
For example, you can use the Get-ADUser cmdlet to retrieve a user object and then pass the object through the pipeline to the Set-ADUser cmdlet.

The Instance parameter provides a way to update a user object by applying the changes made to a copy of the object.
When you set the Instance parameter to a copy of an Active Directory user object that has been modified, the Set-ADUser cmdlet makes the same changes to the original user object.
To get a copy of the object to modify, use the Get-ADUser object.
The Identity parameter is not allowed when you use the Instance parameter.
For more information about the Instance parameter, see the Instance parameter description.
For more information about how the Instance concept is used in Active Directory cmdlets, see about_ActiveDirectory_Instance.

Accounts created with the New-ADUser cmdlet will be disabled if no password is provided.

The following examples show how to modify the Manager property of a user object by using three methods:

-By specifying the Identity and the Manager parameters

-By passing a user object through the pipeline and specifying the Manager parameter

-By specifying the Instance parameter.

Method 1: Modify the Manager property for the "saraDavis" user by using the Identity and Manager parameters.

Set-ADUser -Identity "saraDavis" -Manager "JimCorbin"

Method 2: Modify the Manager property for the "saraDavis" user by passing the "saraDavis" user through the pipeline and specifying the Manager parameter.

Get-ADUser -Identity "saraDavis" | Set-ADUser -Manager "JimCorbin"

Method 3: Modify the Manager property for the "saraDavis" user by using the Windows PowerShell command line to modify a local instance of the "saraDavis" user.
Then set the Instance parameter to the local instance.

$user = Get-ADUser -Identity "saraDavis"

$user.Manager = "JimCorbin"

Set-ADUser -Instance $user.

For AD LDS environments, the Partition parameter must be specified except in the following two conditions:

-The cmdlet is run from an Active Directory provider drive.

-A default naming context or partition is defined for the AD LDS environment.
To specify a default naming context for an AD LDS environment, set the msDS-defaultNamingContext property of the Active Directory directory service agent (DSA) object (nTDSDSA) for the AD LDS instance.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Set-ADUser AntonioAl -HomePage 'http://fabrikam.com/employees/AntonioAl' -LogonWorkstations 'AntonioAl-DSKTOP,AntonioAl-LPTOP'
```

Description

-----------

Set the user with samAccountName AntonioAL's property homepage to http://fabrikam.com/employees/AntonioAl and the LogonWorkstations property to AntonioAl-DSKTOP,AntonioAl-LPTOP.

### -------------------------- EXAMPLE 2 --------------------------
```
C:\PS>Get-ADUser -Filter 'Name -like "*"' -SearchBase 'OU=HumanResources,OU=UserAccounts,DC=FABRIKAM,DC=COM' -Properties DisplayName | % {Set-ADUser $_ -DisplayName ($_.Surname + ' ' + $_.GivenName)}
```

Description

-----------

Get all the users in the directory that are located underneath the OU=HumanResources,OU=UserAccounts,DC=FABRIKAM,DC=COM organizationalUnit. 
Set the DisplayName property on these user objects to the concatenation of the Surname property and the GivenName property.

### -------------------------- EXAMPLE 3 --------------------------
```
C:\PS>Set-ADUser GlenJohn -Replace @{title="director";mail="glenjohn@fabrikam.com"}
```

Description

-----------

Set the user with samAccountNAme GlenJohn's property title to director and property mail to glenjohn@fabrikam.com.

### -------------------------- EXAMPLE 4 --------------------------
```
C:\PS>Set-ADUser GlenJohn -Remove @{otherMailbox="glen.john"} -Add @{url="fabrikam.com"} -Replace @{title="manager"} -Clear description
```

Description

-----------

Modify the user with samAccountName GlenJohn's object by removing glen.john from the otherMailbox property, adding fabrikam.com to the url property, replacing the title property with manager and clearing the description property.

### -------------------------- EXAMPLE 5 --------------------------
```
C:\PS>$user = Get-ADUser GlenJohn -Properties mail,department
$user.mail = "glen@fabrikam.com"
$user.department = "Accounting"
Set-ADUser -instance $user
```

Description

-----------

Set the mail and department properties on the user object with samAccountName GlenJohn by using the instance parameter.

### -------------------------- EXAMPLE 6 --------------------------
```
PS C:\># create a byte array for the M-F 8:00 am to 5 pm logon hours


PS C:\>$hours = New-Object byte[] 21


PS C:\>$hours[5] = 255; $hours[8] = 255; $hours[11] = 255; $hours[14] = 255; $hours[17] = 255;


PS C:\>$hours[6] = 1; $hours[9] = 1; $hours[12] = 1; $hours[15] = 1; $hours[18] = 1;


PS C:\># create a hashtable to update the logon hours and a description


PS C:\>$replaceHashTable = New-Object HashTable


PS C:\>$replaceHashTable.Add("logonHours", $hours)


PS C:\>$replaceHashTable.Add("description", "Sarah Davis can only logon from Monday through Friday from 8:00 AM to 5:00 PM")


PS C:\># set the value of the logonHours and description attributes


PS C:\>Set-ADUser "SarahDavis" -Replace $replaceHashTable
```

Description

-----------

Set the user logon hours to Monday through Friday from 8:00 AM to 5:00 PM and add a description.
It updates the "logonHours" attribute with the specified byte array and the description attribute with the specified string.

### -------------------------- EXAMPLE 7 --------------------------
```
PS C:\>$manager = Get-ADUser GlenJohn -Server Corp-DC01


PS C:\>Set-ADUser AntonioAl -Manager $manager -Server Branch-DC02
```

Description

-----------

Set the Manager property for user with samAccountName of "AntonioAL" where the manager (GlenJohn) is a user in another domain.

## PARAMETERS

### -AccountExpirationDate
Specifies the expiration date for an account.
When you set this parameter to 0, the account never expires.
This parameter sets the AccountExpirationDate property of an account object.
The LDAP Display name (ldapDisplayName) for this property is accountExpires.

Use the DateTime syntax when you specify this parameter.
Time is assumed to be local time unless otherwise specified.
When a time value is not specified, the time is assumed to 12:00:00 AM local time.
When a date is not specified, the date is assumed to be the current date.
The following examples show commonly-used syntax to specify a DateTime object.

"4/17/2006"

"Monday, April 17, 2006"

"2:22:45 PM"

"Monday, April 17, 2006 2:22:45 PM"

These examples specify the same date and the time without the seconds.

"4/17/2006 2:22 PM"

"Monday, April 17, 2006 2:22 PM"

"2:22 PM"

The following example shows how to specify a date and time by using the RFC1123 standard.
This example defines time by using Greenwich Mean Time (GMT).

"Mon, 17 Apr 2006 21:22:48 GMT"

The following example shows how to specify a round-trip value as Coordinated Universal Time (UTC).
This example represents Monday, April 17, 2006 at 2:22:48 PM UTC.

"2006-04-17T14:22:48.0000000"

The following example shows how to set this parameter to the date May 1, 2012 at 5 PM.

-AccountExpirationDate "05/01/2012 5:00:00 PM"

```yaml
Type: DateTime
Parameter Sets: Identity
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AccountNotDelegated
Specifies whether the security context of the user is delegated to a service.
When this parameter is set to true, the security context of the account is not delegated to a service even when the service account is set as trusted for Kerberos delegation.
This parameter sets the AccountNotDelegated property for an Active Directory account.
This parameter also sets the ADS_UF_NOT_DELEGATED flag of the Active Directory User Account Control (UAC) attribute.
Possible values for this parameter include

$false or 0

$true or 1

The following example shows how to set this parameter so that the security context of the account is not delegated to a service.

-AccountNotDelegated $true

```yaml
Type: Boolean
Parameter Sets: Identity
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -AllowReversiblePasswordEncryption
Specifies whether reversible password encryption is allowed for the account.
This parameter sets the AllowReversiblePasswordEncryption property of the account.
This parameter also sets the ADS_UF_ENCRYPTED_TEXT_PASSWORD_ALLOWED flag of the Active Directory User Account Control (UAC) attribute.
Possible values for this parameter include:

$false or 0

$true or 1

The following example shows how to set this parameter to true.

-AllowReversiblePasswordEncryption $true

```yaml
Type: Boolean
Parameter Sets: Identity
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

### -CannotChangePassword
Specifies whether the account password can be changed.
This parameter sets the CannotChangePassword property of an account.
Possible values for this parameter include:

$false or 0

$true or 1

The following example shows how to set this parameter so that the account password can be changed.

-CannotChangePassword $false

```yaml
Type: Boolean
Parameter Sets: Identity
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Certificates
Modifies the DER-encoded X.509v3 certificates of the account.
These certificates include the public key certificates issued to this account by the Microsoft Certificate Service.
This parameter sets the Certificates property of the account object.
The LDAP Display Name (ldapDisplayName) for this property is "userCertificate".

Syntax:

To add values:

-Certificates @{Add=value1,value2,...}

To remove values:

-Certificates @{Remove=value3,value4,...}

To replace values:

-Certificates @{Replace=value1,value2,...}

To clear all values:

-Certificates $null

You can specify more than one operation by using a list separated by semicolons.
For example, use the following syntax to add and remove Certificate values

-Certificates @{Add=value1,value2,...};@{Remove=value3,value4,...}

The operators will be applied in the following sequence:

..Remove

..Add

..Replace

The following example shows how to create a certificate by using the New-Object cmdlet, and then add it to a user account.
When this cmdlet is run, \<certificate password\> is replaced by the password used to add the certificate.

$cert = New-Object System.Security.Cryptography.X509Certificates.X509Certificate certificate1.cer  \<certificate password\>

Set-ADUser saradavis  -Certificates @{Add=$cert}

The following example shows how to add a certificate that is specified as a byte array.

Set-ADUser saradavis  -Certificates @{Add= \[Byte\[\]\](0xC5,0xEE,0x53,...)}

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

### -ChangePasswordAtLogon
Specifies whether a password must be changed during the next logon attempt.
Possible values for this parameter include:

$false or 0

$true or 1

This parameter cannot be set to $true or 1 for an account that also has the PasswordNeverExpires property set to true.

The following example shows how to set this parameter so that the password must be changed at logon.

-ChangePasswordAtLogon $true

```yaml
Type: Boolean
Parameter Sets: Identity
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -City
Specifies the user's town or city.
This parameter sets the City property of a user.
The LDAP display name (ldapDisplayName) of this property is "l".

The following example shows how set this parameter.

-City "Las Vegas"

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

### -Company
Specifies the user's company.
This parameter sets the Company property of a user object.
The LDAP display name (ldapDisplayName) of this property is "company".

The following example shows how to set this parameter.

-Company "Contoso"

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

### -CompoundIdentitySupported
Specifies whether an account supports Kerberos service tickets which includes the authorization data for the user's device. 
This value sets the compound identity supported flag of the Active Directory msDS-SupportedEncryptionTypes attribute.
Possible values for this parameter are:

$false or 0

$true or 1

The following example shows how to specify that an account supports service tickets with device authorization data.

-SupportDeviceAuthz $true

Warning: Domain-joined Windows systems and services such as clustering manage their own msDS-SupportedEncryptionTypes attribute.
Therefore any changes to the flag on the msDS-SupportedEncryptionTypes attribute will be overwritten by the service or system which manages the setting.

```yaml
Type: Boolean
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

### -Country
Specifies the country or region code for the user's language of choice.
This parameter sets the Country property of a user object.
The LDAP Display Name (ldapDisplayName) of this property is "c".
This value is not used by Windows 2000.

The following example shows how set this parameter.

-Country "IN"

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

### -Department
Specifies the user's department.
This parameter sets the Department property of a user.
The LDAP Display Name (ldapDisplayName) of this property is "department".

The following example shows how to set this parameter.

-Department "Development"

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

### -Description
Specifies a description of the object.
This parameter sets the value of the Description property for the object.
The LDAP Display Name (ldapDisplayName) for this property is "description".

The following example shows how to set this parameter to a sample description.

-Description "Description of the object"

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

### -DisplayName
Specifies the display name of the object.
This parameter sets the DisplayName property of the object.
The LDAP Display Name (ldapDisplayName) for this property is "displayName".

The following example shows how to set this parameter.

-DisplayName "Sara Davis Laptop"

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

### -Division
Specifies the user's division.
This parameter sets the Division property of a user object.
The LDAP Display Name (ldapDisplayName) of this property is "division".

The following example shows how to set this parameter.

-Division "Software"

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

### -EmailAddress
Specifies the user's e-mail address.
This parameter sets the EmailAddress property of a user object.
The LDAP Display Name (ldapDisplayName) of this property is "mail".

The following example shows how to set this parameter.

-EmailAddress "saradavis@contoso.com"

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

### -EmployeeID
Specifies the user's employee ID.
This parameter sets the EmployeeID property of a user object.
The LDAP Display Name (ldapDisplayName) of this property is "employeeID".

The following example shows how to set this parameter.

-EmployeeID  "A123456"

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

### -EmployeeNumber
Specifies the user's employee number.
This parameter sets the EmployeeNumber property of a user object.
The LDAP Display Name (ldapDisplayName) of this property is "employeeNumber".

The following example shows how set this parameter.

-EmployeeNumber "12345678"

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

### -Enabled
Specifies if an account is enabled.
An enabled account requires a password.
This parameter sets the Enabled property for an account object.
This parameter also sets the ADS_UF_ACCOUNTDISABLE flag of the Active Directory User Account Control (UAC) attribute.
Possible values for this parameter include:

$false or 0

$true or 1

The following example shows how to set this parameter to enable the account.

-Enabled $true

```yaml
Type: Boolean
Parameter Sets: Identity
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Fax
Specifies the user's fax phone number.
This parameter sets the Fax property of a user object.
The LDAP Display Name (ldapDisplayName) of this property is "facsimileTelephoneNumber".

The following example shows how to set this parameter.

-Fax  "+1 (999) 555 1212"

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

### -GivenName
Specifies the user's given name.
This parameter sets the GivenName property of a user object.
The LDAP Display Name (ldapDisplayName) of this property is "givenName".

The following example shows how to set this parameter.

-givenName "Sanjay"

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

### -HomeDirectory
Specifies a user's home directory.
This parameter sets the HomeDirectory property of a user object.
The LDAP Display Name (ldapDisplayName) for this property is "homeDirectory".

The following example shows how to set this parameter.

-HomeDirectory "\\\\users\saraDavisHomeDir"

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

### -HomeDrive
Specifies a drive that is associated with the UNC path defined by the HomeDirectory property.
The drive letter is specified as "\<DriveLetter\>:" where \<DriveLetter\> indicates the letter of the drive to associate.
The \<DriveLetter\> must be a single, uppercase letter and the colon is required.
This parameter sets the HomeDrive property of the user object.
The LDAP Display Name (ldapDisplayName) for this property is "homeDrive".

The following example shows how to set this parameter.

-HomeDrive "D:"

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

### -HomePage
Specifies the URL of the home page of the object.
This parameter sets the homePage property of an Active Directory object.
The LDAP Display Name (ldapDisplayName) for this property is "wWWHomePage".

The following example shows how to set this parameter to a URL.

-HomePage "http://employees.contoso.com/sdavis"

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

### -HomePhone
Specifies the user's home telephone number.
This parameter sets the HomePhone property of a user.
The LDAP Display Name (ldapDisplayName) of this property is "homePhone".

The following example shows how to set this parameter.

-HomePhone  "+1 (999) 555 1212"

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

### -Identity
Specifies an Active Directory user object by providing one of the following property values.
The identifier in parentheses is the LDAP display name for the attribute.

Distinguished Name

Example:  CN=SaraDavis,CN=Europe,CN=Users,DC=corp,DC=contoso,DC=com

GUID (objectGUID)

Example: 599c3d2e-f72d-4d20-8a88-030d99495f20

Security Identifier (objectSid)

Example: S-1-5-21-3165297888-301567370-576410423-1103

SAM account name  (sAMAccountName)

Example: saradavis

The cmdlet searches the default naming context or partition to find the object.
If two or more objects are found, the cmdlet returns a non-terminating error.

This parameter can also get this object through the pipeline or you can set this parameter to an object instance.

This example shows how to set the parameter to a distinguished name.

-Identity  "CN=SaraDavis,CN=Europe,CN=Users,DC=corp,DC=contoso,DC=com"

This example shows how to set this parameter to a user object instance named "userInstance".

-Identity   $userInstance

```yaml
Type: ADUser
Parameter Sets: Identity
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Initials
Specifies the initials that represent part of a user's name.
You can use this value for the user's middle initial.
This parameter sets the Initials property of a user.
The LDAP Display Name (ldapDisplayName) of this property is "initials".

The following example shows how set this parameter.

-Initials "L"

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

### -Instance
Specifies an ADUser object that identifies the Active Directory user object that should be modified and the set of changes that should be made to that object.
When this parameter is used, any modifications made to the ADUser object are also made to the corresponding Active Directory object.
The cmdlet only updates the object properties that have changed.

The ADUser object specified as the value of the -Instance parameter must have been retrieved by using the Get-ADUser cmdlet.
When you specify the Instance parameter, you cannot specify other parameters that set individual properties on the object.

The following is an example of how to use the Get-ADUser cmdlet to retrieve an instance of the ADUser object.
The object is modified by using the Windows PowerShell command line.
Then the Set-ADUser cmdlet saves the changes to the Active Directory object.

Step 1: Retrieve a local instance of the object.

$userInstance = Get-ADUser  -Identity saraDavis

Step 2: Modify one or more properties of the object instance.

$userInstance.EmailAddress = "saradavis@contoso.com"

Step3: Save your changes to saraDavis.

Set-ADUser -Instance $userInstance

```yaml
Type: ADUser
Parameter Sets: Instance
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KerberosEncryptionType
Specifies whether an account supports Kerberos encryption types which are used during creation of service tickets. 
This value sets the encryption types supported flags of the Active Directory msDS-SupportedEncryptionTypes attribute.
Possible values for this parameter are:

None

DES

RC4

AES128

AES256

None, will remove all encryption types from the account resulting the KDC being unable to issue service tickets for services using the account.

DES is a weak encryption type which is not supported by default since Windows 7 and Windows Server 2008 R2.

The following example shows how to specify that an account supports service tickets with device authorization data.

-KerberosEncryptionTypes RC4|AES128|AES256

Warning: Domain-joined Windows systems and services such as clustering manage their own msDS-SupportedEncryptionTypes attribute.
Therefore any changes to the flag on the msDS-SupportedEncryptionTypes attribute will be overwritten by the service or system which manages the setting.

```yaml
Type: ADKerberosEncryptionType
Parameter Sets: Identity
Aliases: 
Accepted values: None, DES, RC4, AES128, AES256

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogonWorkstations
Specifies the computers that the user can access.
To specify more than one computer, create a single comma-separated list.
You can identify a computer by using the Security Accounts Manager (SAM) account name (sAMAccountName) or the DNS host name of the computer.
The SAM account name is the same as the NetBIOS name of the computer.

The LDAP display name (ldapDisplayName) for this property is "userWorkStations".

The following example shows how to set this parameter by using SAMAccountName (NetBIOS name) and DNSHostName values.

-LogonWorkstations "saraDavisDesktop,saraDavisLapTop,projectA.corp.contoso.com"

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

### -Manager
Specifies the user's manager.
This parameter sets the Manager property of a user.
This parameter is set by providing one of the following property values. 
Note: The identifier in parentheses is the LDAP display name for the property.

Distinguished Name

Example: CN=SaraDavis,CN=Europe,CN=Users,DC=corp,DC=contoso,DC=com

GUID (objectGUID)

Example: 599c3d2e-f72d-4d20-8a88-030d99495f20

Security Identifier (objectSid)

Example: S-1-5-21-3165297888-301567370-576410423-1103

SAM Account Name (sAMAccountName)

Example: saradavis

The LDAP Display Name (ldapDisplayName) of this property is "manager".

The following example shows how to set this parameter.

-Manager saradavis

```yaml
Type: ADUser
Parameter Sets: Identity
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MobilePhone
Specifies the user's mobile phone number.
This parameter sets the MobilePhone property of a user object.
The LDAP Display Name (ldapDisplayName) of this property is "mobile".

The following example shows how to set this parameter.

-MobilePhone  "+1  (999 ) 555 1212"

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

### -Office
Specifies the location of the user's office or place of business.
This parameter sets the Office property of a user object.
The LDAP display name (ldapDisplayName) of this property is "office".

The following example shows how to set this parameter.

-Office  "D1042"

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

### -OfficePhone
Specifies the user's office telephone number.
This parameter sets the OfficePhone property of a user object.
The LDAP display name (ldapDisplayName) of this property is "telephoneNumber".

The following example shows how to set this parameter.

-OfficePhone  "+1 (999) 555 1212"

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

### -Organization
Specifies the user's organization.
This parameter sets the Organization property of a user object.
The LDAP display name (ldapDisplayName) of this property is "o".

The following example shows how to set this parameter.

-Organization "Accounting"

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

### -OtherName
Specifies a name in addition to a user's given name and surname, such as the user's middle name.
This parameter sets the OtherName property of a user object.
The LDAP Display Name (ldapDisplayName) of this property is "middleName".

The following example shows how to set this parameter.

-OtherName  "Peter"

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

### -POBox
Specifies the user's post office box number.
This parameter sets the POBox property of a user object.
The LDAP Display Name (ldapDisplayName) of this property is "postOfficeBox".

The following example shows how to set this parameter.

-POBox  "25662"

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

### -PasswordNeverExpires
Specifies whether the password of an account can expire.
This parameter sets the PasswordNeverExpires property of an account object.
This parameter also sets the ADS_UF_DONT_EXPIRE_PASSWD flag of the Active Directory User Account Control attribute.
Possible values for this parameter include:

$false or 0

$true or 1

Note: This parameter cannot be set to $true or 1 for an account that also has the ChangePasswordAtLogon property set to true.

The following example shows how to set this parameter so that the password can expire.

-PasswordNeverExpires $false

```yaml
Type: Boolean
Parameter Sets: Identity
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PasswordNotRequired
Specifies whether the account requires a password.
This parameter sets the PasswordNotRequired property of an account, such as a user or computer account.
This parameter also sets the ADS_UF_PASSWD_NOTREQD flag of the Active Directory User Account Control attribute.
Possible values for this parameter are:

$false or 0

$true or 1

The following example shows how to set this parameter so that as password is not required for the account.

-PasswordNotRequired $true

```yaml
Type: Boolean
Parameter Sets: Identity
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PostalCode
Specifies the user's postal code or zip code.
This parameter sets the PostalCode property of a user.
The LDAP Display Name (ldapDisplayName) of this property is "postalCode".

The following example shows how to set this parameter.

-PostalCode "28712"

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

### -PrincipalsAllowedToDelegateToAccount
This parameter sets the msDS-AllowedToActOnBehalfOfOtherIdentity attribute of a computer account object.

```yaml
Type: ADPrincipal[]
Parameter Sets: Identity
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProfilePath
Specifies a path to the user's profile.
This value can be a local absolute path or a Universal Naming Convention (UNC) path.
This parameter sets the ProfilePath property of the user object.
The LDAP display name (ldapDisplayName) for this property is "profilePath".

The following examples show how to set this parameter to a local path and to a UNC path. 
-ProfilePath "E:\users\profiles\saraDavis"

-ProfilePath "\\\\users\profiles\saraDavis"

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

### -SamAccountName
Specifies the Security Account Manager (SAM) account name of the user, group, computer, or service account.
The maximum length of the description is 256 characters.
To be compatible with older operating systems, create a SAM account name that is 20 characters or less.
This parameter sets the SAMAccountName for an account object.
The LDAP display name (ldapDisplayName) for this property is "sAMAccountName".

The following example shows how to specify this parameter.

-SAMAccountName "saradavis"

Note: If the string value provided is not terminated with a '$' character, the system adds one if needed.

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

### -ScriptPath
Specifies a path to the user's log on script.
This value can be a local absolute path or a Universal Naming Convention (UNC) path.
This parameter sets the ScriptPath property of the user.
The LDAP display name (ldapDisplayName) for this property is "scriptPath".

The following example shows how to set this parameter.

-ScriptPath "\\\\logonScripts\saradavisLogin"

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

### -ServicePrincipalNames
Specifies the service principal names for the account.
This parameter sets the ServicePrincipalNames property of the account.
The LDAP display name (ldapDisplayName) for this property is servicePrincipalName.
This parameter uses the following syntax to add remove, replace or clear service principal name values.

Syntax:

To add values:

-ServicePrincipalNames @{Add=value1,value2,...}

To remove values:

-ServicePrincipalNames @{Remove=value3,value4,...}

To replace values:

-ServicePrincipalNames @{Replace=value1,value2,...}

To clear all values:

-ServicePrincipalNames $null

You can specify more than one change by using a list separated by semicolons.
For example, use the following syntax to add and remove service principal names.

@{Add=value1,value2,...};@{Remove=value3,value4,...}

The operators will be applied in the following sequence:

..Remove

..Add

..Replace

The following example shows how to add and remove service principal names.

-ServicePrincipalNames-@{Add="SQLservice\accounting.corp.contoso.com:1456"};{Remove="SQLservice\finance.corp.contoso.com:1456"}

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

### -SmartcardLogonRequired
Specifies whether a smart card is required to logon.
This parameter sets the SmartCardLoginRequired property for a user.
This parameter also sets the ADS_UF_SMARTCARD_REQUIRED flag of the Active Directory User Account Control attribute.
Possible values for this parameter are:

$false or 0

$true or 1

The following example shows how to set this parameter so that a smart card is required to logon to the account.

-SmartCardLogonRequired $true

```yaml
Type: Boolean
Parameter Sets: Identity
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -State
Specifies the user's or Organizational Unit's state or province.
This parameter sets the State property of a User or Organizational Unit object.
The LDAP display name (ldapDisplayName) of this property is "st".

The following example shows how set this parameter.

-State  "Nevada"

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

### -StreetAddress
Specifies the user's street address.
This parameter sets the StreetAddress property of a user object.
The LDAP display name (ldapDisplayName) of this property is "streetAddress".

The following example shows how to set this parameter.

-StreetAddress  "1200 Main Street"

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

### -Surname
Specifies the user's last name or surname.
This parameter sets the Surname property of a user object.
The LDAP display name (ldapDisplayName) of this property is "sn".

The following example shows how to set this parameter.

-Surname  "Patel"

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

### -Title
Specifies the user's title.
This parameter sets the Title property of a user object.
The LDAP display name (ldapDisplayName) of this property is "title".

The following example shows how to set this parameter.

-Title  "Manager"

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

### -TrustedForDelegation
Specifies whether an account is trusted for Kerberos delegation.
A service that runs under an account that is trusted for Kerberos delegation can assume the identity of a client requesting the service.
This parameter sets the TrustedForDelegation property of an account object.
This value also sets the ADS_UF_TRUSTED_FOR_DELEGATION flag of the Active Directory User Account Control attribute.
Possible values for this parameter are:

$false or 0

$true or 1

The following example shows how to specify that an account is trusted for Kerberos delegation.

-TrustedForDelegation $true

```yaml
Type: Boolean
Parameter Sets: Identity
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserPrincipalName
Each user account has a user principal name (UPN) in the format \<user\>@\<DNS-domain-name\>.
A UPN is a friendly name assigned by an administrator that is shorter than the LDAP distinguished name used by the system and easier to remember.
The UPN is independent of the user object's DN, so a user object can be moved or renamed without affecting the user logon name.
When logging on using a UPN, users no longer have to choose a domain from a list on the logon dialog box.

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

### None or Microsoft.ActiveDirectory.Management.ADUser
A user object is received by the Identity parameter.

A user object that was retrieved by using the Get-ADUser cmdlet and then modified is received by the Instance parameter.

## OUTPUTS

### None or Microsoft.ActiveDirectory.Management.ADUser
Returns the modified user object when the PassThru parameter is specified.
By default, this cmdlet does not generate any output.

## NOTES
* This cmdlet does not work with an Active Directory Snapshot.

  This cmdlet does not work with a read-only domain controller.

## RELATED LINKS

[Get-ADUser](./Get-ADUser.md)

[New-ADUser](./New-ADUser.md)

[Remove-ADUser](./Remove-ADUser.md)

[Set-ADAccountControl](./Set-ADAccountControl.md)

