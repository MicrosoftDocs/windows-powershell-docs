---
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
ms.assetid: 4B247B2D-FB03-48D2-BAC7-ACD366A7CC8E
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# New-ADUser

## SYNOPSIS
Creates a new Active Directory user.

## SYNTAX

```
New-ADUser [-WhatIf] [-Confirm] [-AccountExpirationDate <DateTime>] [-AccountNotDelegated <Boolean>]
 [-AccountPassword <SecureString>] [-AllowReversiblePasswordEncryption <Boolean>] [-AuthType <ADAuthType>]
 [-CannotChangePassword <Boolean>] [-Certificates <X509Certificate[]>] [-ChangePasswordAtLogon <Boolean>]
 [-City <String>] [-Company <String>] [-CompoundIdentitySupported <Boolean>] [-Country <String>]
 [-Credential <PSCredential>] [-Department <String>] [-Description <String>] [-DisplayName <String>]
 [-Division <String>] [-EmailAddress <String>] [-EmployeeID <String>] [-EmployeeNumber <String>]
 [-Enabled <Boolean>] [-Fax <String>] [-GivenName <String>] [-HomeDirectory <String>] [-HomeDrive <String>]
 [-HomePage <String>] [-HomePhone <String>] [-Initials <String>] [-Instance <ADUser>]
 [-KerberosEncryptionType <ADKerberosEncryptionType>] [-LogonWorkstations <String>] [-Manager <ADUser>]
 [-MobilePhone <String>] [-Name] <String> [-Office <String>] [-OfficePhone <String>] [-Organization <String>]
 [-OtherAttributes <Hashtable>] [-OtherName <String>] [-PassThru] [-PasswordNeverExpires <Boolean>]
 [-PasswordNotRequired <Boolean>] [-Path <String>] [-POBox <String>] [-PostalCode <String>]
 [-PrincipalsAllowedToDelegateToAccount <ADPrincipal[]>] [-ProfilePath <String>] [-SamAccountName <String>]
 [-ScriptPath <String>] [-Server <String>] [-ServicePrincipalNames <String[]>]
 [-SmartcardLogonRequired <Boolean>] [-State <String>] [-StreetAddress <String>] [-Surname <String>]
 [-Title <String>] [-TrustedForDelegation <Boolean>] [-Type <String>] [-UserPrincipalName <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The New-ADUser cmdlet creates a new Active Directory user.
You can set commonly used user property values by using the cmdlet parameters.

Property values that are not associated with cmdlet parameters can be set by using the OtherAttributes parameter. 
When using this parameter be sure to place single quotes around the attribute name as in the following example.

New-ADUser -SamAccountName "glenjohn"  -GivenName "Glen" -Surname "John" -DisplayName "Glen John" -Path 'CN=Users,DC=fabrikam,DC=local' -OtherAttributes @{'msDS-PhoneticDisplayName'="GlenJohn"}

You must specify the SAMAccountName parameter to create a user.

You can use the New-ADUser cmdlet to create different types of user accounts such as iNetOrgPerson accounts.
To do this in AD DS, set the Type parameter to the LDAP display name for the type of account you want to create.
This type can be any class in the Active Directory schema that is a subclass of user and that has an object category of person.

The Path parameter specifies the container or organizational unit (OU) for the new user.
When you do not specify the Path parameter, the cmdlet creates a user object in the default container for user objects in the domain.

The following methods explain different ways to create an object by using this cmdlet.

Method 1: Use the New-ADUser cmdlet, specify the required parameters, and set any additional property values by using the cmdlet parameters.

Method 2: Use a template to create the new object.
To do this, create a new user object or retrieve a copy of an existing user object and set the Instance parameter to this object.
The object provided to the Instance parameter is used as a template for the new object.
You can override property values from the template by setting cmdlet parameters.
For examples and more information, see the Instance parameter description for this cmdlet.

Method 3: Use the Import-CSV cmdlet with the New-ADUser cmdlet to create multiple Active Directory user objects.
To do this, use the Import-CSV cmdlet to create the custom objects from a comma-separated value (CSV) file that contains a list of object properties.
Then pass these objects through the pipeline to the New-ADUser cmdlet to create the user objects.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>New-ADUser GlenJohn -Certificate (new-object System.Security.Cryptography.X509Certificates.X509Certificate -ArgumentList "export.cer")
```

Description

-----------

Create a new user named 'GlenJohn' with a certificate imported from the file "export.cer".

### -------------------------- EXAMPLE 2 --------------------------
```
C:\PS>New-ADUser GlenJohn -OtherAttributes @{title="director";mail="glenjohn@fabrikam.com"}
```

Description

-----------

Create a new user named 'GlenJohn' and set the title and mail properties on the new object.

### -------------------------- EXAMPLE 3 --------------------------
```
C:\PS>New-ADUser GlenJohn -Type iNetOrgPerson -Path "DC=AppNC" -server lds.Fabrikam.com:50000
```

Description

-----------

Create a new inetOrgPerson named 'GlenJohn' on an AD LDS instance.

## PARAMETERS

### -AccountExpirationDate
Specifies the expiration date for an account.
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
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AccountPassword
Specifies a new password value for an account.
This value is stored as an encrypted string.

The following conditions apply based on the manner in which the password parameter is used:

$null password is specified - No password is set and the account is disabled unless it is requested to be enabled

No password is specified - No password is set and the account is disabled unless it is requested to be enabled

User password is specified - Password is set and the account is disabled unless it is requested to be enabled

Notes:

User accounts, by default, are created without a password.
If you provide a password, an attempt will be made to set that password however, this can fail due to password policy restrictions.
The user account will still be created and you may use Set-ADAccountPassword to set the password on that account.
In order to ensure that accounts remain secure, user accounts will never be enabled unless a valid password is set or PasswordNotRequired is set to true.

The account is created if the password fails for any reason.

The following example shows one method to set this parameter.
This command will prompt you to enter the password.

-AccountPassword (Read-Host -AsSecureString "AccountPassword")

```yaml
Type: SecureString
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Certificates
Specifies the DER-encoded X.509v3 certificates of the account. These certificates include the public key certificates issued to this account by the Microsoft Certificate Service. This parameter sets the Certificates property of the account object. The LDAP display name (ldapDisplayName) for this property is userCertificate. 

```yaml
Type: X509Certificate[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Instance
Specifies an instance of a user object to use as a template for a new user object.

You can use an instance of an existing user object as a template or you can construct a new user object for template use. 
You can construct a new user object using the Windows PowerShell command line or by using a script.
The following examples show how to use these two methods to create user object templates.

Method 1: Use an existing user object as a template for a new object.
To retrieve an instance of an existing user object, use a cmdlet such as Get-ADUser.
Then provide this object to the Instance parameter of the New-ADUser cmdlet to create a new user object.
You can override property values of the new object by setting the appropriate parameters.

$userInstance = Get-ADUser -Identity "saraDavis"

New-ADUser -SAMAccountName "ellenAdams"  -Instance $userInstance -DisplayName "EllenAdams"

Method 2: Create a new ADUser object and set the property values by using the Windows PowerShell command line interface.
Then pass this object to the Instance parameter of the New-ADUser cmdlet to create the new Active Directory user object.

$userInstance = new-object Microsoft.ActiveDirectory.Management.ADUser

$userInstance.DisplayName = "Ellen Adams"

New-ADUser -SAMAccountName "ellenAdams"  -Instance $userInstance

Note: Specified attributes are not validated, so attempting to set attributes that do not exist or cannot be set will raise an error.

```yaml
Type: ADUser
Parameter Sets: (All)
Aliases: 

Required: False
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
Parameter Sets: (All)
Aliases: 
Accepted values: None, DES, RC4, AES128, AES256

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of the object.
This parameter sets the Name property of the Active Directory object.
The LDAP Display Name (ldapDisplayName) of this property is "name".

The following example shows how to set this parameter to a name string.

-Name "SaraDavis"

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -OtherAttributes
Specifies object attribute values for attributes that are not represented by cmdlet parameters.
You can set one or more parameters at the same time with this parameter.
If an attribute takes more than one value, you can assign multiple values.
To identify an attribute, specify the LDAPDisplayName (ldapDisplayName) defined for it in the Active Directory schema.

Syntax:

To specify a single value for an attribute:

-OtherAttributes @{'AttributeLDAPDisplayName'=value}

To specify multiple values for an attribute

-OtherAttributes @{'AttributeLDAPDisplayName'=value1,value2,...}

You can specify values for more than one attribute by using semicolons to separate attributes. 
The following syntax shows how to set values for multiple attributes:

-OtherAttributes @{'Attribute1LDAPDisplayName'=value; 'Attribute2LDAPDisplayName'=value1,value2;...}

The following examples show how to use this parameter.

To set the value of a custom attribute called favColors that takes a set of Unicode strings, use the following syntax:

-OtherAttributes @{'favColors'="pink","purple"}

To set values for favColors and dateOfBirth simultaneously, use the following syntax:

-OtherAttributes @{'favColors'="pink","purple"; 'dateOfBirth'=" 01/01/1960"}

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

### -OtherName
Specifies a name in addition to a user's given name and surname, such as the user's middle name.
This parameter sets the OtherName property of a user object.
The LDAP Display Name (ldapDisplayName) of this property is "middleName".

The following example shows how to set this parameter.

-OtherName  "Peter"

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PasswordNotRequired
Specifies whether the account requires a password.
A password is not required for a new account.
This parameter sets the PasswordNotRequired property of an account object.

The following example shows how to set this parameter to true.

-PasswordNotRequired $true

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path
Specifies the X.500 path of the Organizational Unit (OU) or container where the new object is created.

In many cases, a default value will be used for the Path parameter if no value is specified. 
The rules for determining the default value are given below. 
Note that rules listed first are evaluated first and once a default value can be determined, no further rules will be evaluated.

In AD DS environments, a default value for Path will be set in the following cases:

- If the cmdlet is run from an Active Directory PowerShell provider drive, the parameter is set to the current path of the provider drive.
- If the cmdlet has a default path, this will be used.  For example: in New-ADUser, the Path parameter would default to the Users container.
- If none of the previous cases apply, the default value of Path will be set to the default partition or naming context of the target domain.

In AD LDS environments, a default value for Path will be set in the following cases:

- If the cmdlet is run from an Active Directory PowerShell provider drive, the parameter is set to the current path of the provider drive.
- If the cmdlet has a default path, this will be used.  For example: in New-ADUser, the Path parameter would default to the Users container.
- If the target AD LDS instance has a default naming context, the default value of Path will be set to the default naming context.  To specify a default naming context for an AD LDS environment, set the msDS-defaultNamingContext property of the Active Directory directory service agent (DSA) object (nTDSDSA) for the AD LDS instance.
- If none of the previous cases apply, the Path parameter will not take any default value.

The following example shows how to set this parameter to an OU.

-Path "ou=mfg,dc=noam,dc=corp,dc=contoso,dc=com"

Note:  The Active Directory Provider cmdlets, such New-Item, Remove-Item, Remove-ItemProperty, Rename-Item and Set-ItemProperty also contain a Path property.
However, for the provider cmdlets, the Path parameter identifies the path of the actual object and not the container as with the Active Directory cmdlets.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PrincipalsAllowedToDelegateToAccount
This parameter sets the msDS-AllowedToActOnBehalfOfOtherIdentity attribute of a computer account object.

```yaml
Type: ADPrincipal[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Accept pipeline input: True (ByPropertyName)
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
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
To enter multiple values, use the following syntax: `<value1>,<value2>,...<valueX>`. If the values contain spaces or otherwise require quotation marks, use the following syntax: `"<value1>","<value2>",..."<valueX>"`."

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Type
Specifies the type of object to create.
Set the Type parameter to the LDAP display name of the Active Directory Schema Class that represents the type of object that you want to create.
The selected type must be a subclass of the User schema class. 
If this parameter is not specified it will default to "User".

The following example shows how to use this parameter to create a new Active Directory InetOrgPerson object.

-Type "InetOrgPerson"

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: User
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UserPrincipalName
Each user account has a user principal name (UPN) in the format \<user\>@\<DNS-domain-name\>.
A UPN is a friendly name assigned by an administrator that is shorter than the LDAP distinguished name used by the system and easier to remember.
The UPN is independent of the user object's DN, so a user object can be moved or renamed without affecting the user logon name.
When logging on using a UPN, users no longer have to choose a domain from a list on the logon dialog box.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
A user object that is a template for the new user object is received by the Instance parameter.

## OUTPUTS

### None or Microsoft.ActiveDirectory.Management.ADUser
Returns the new user object when the PassThru parameter is specified.
By default, this cmdlet does not generate any output.

## NOTES
* This cmdlet does not work with an Active Directory Snapshot.
* This cmdlet does not work with a read-only domain controller.

## RELATED LINKS

[Get-ADUser](./Get-ADUser.md)

[Remove-ADUser](./Remove-ADUser.md)

[Set-ADUser](./Set-ADUser.md)

