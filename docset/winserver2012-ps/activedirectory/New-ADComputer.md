---
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
online version: https://learn.microsoft.com/powershell/module/activedirectory/new-adcomputer?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# New-ADComputer

## SYNOPSIS
Creates a new Active Directory computer.

## SYNTAX

```
New-ADComputer [-WhatIf] [-Confirm] [-AccountExpirationDate <DateTime>] [-AccountNotDelegated <Boolean>]
 [-AccountPassword <SecureString>] [-AllowReversiblePasswordEncryption <Boolean>] [-AuthType <ADAuthType>]
 [-CannotChangePassword <Boolean>] [-Certificates <X509Certificate[]>] [-ChangePasswordAtLogon <Boolean>]
 [-CompoundIdentitySupported <Boolean>] [-Credential <PSCredential>] [-Description <String>]
 [-DisplayName <String>] [-DNSHostName <String>] [-Enabled <Boolean>] [-HomePage <String>]
 [-Instance <ADComputer>] [-KerberosEncryptionType <ADKerberosEncryptionType>] [-Location <String>]
 [-ManagedBy <ADPrincipal>] [-Name] <String> [-OperatingSystem <String>] [-OperatingSystemHotfix <String>]
 [-OperatingSystemServicePack <String>] [-OperatingSystemVersion <String>] [-OtherAttributes <Hashtable>]
 [-PassThru] [-PasswordNeverExpires <Boolean>] [-PasswordNotRequired <Boolean>] [-Path <String>]
 [-PrincipalsAllowedToDelegateToAccount <ADPrincipal[]>] [-SAMAccountName <String>] [-Server <String>]
 [-ServicePrincipalNames <String[]>] [-TrustedForDelegation <Boolean>] [-UserPrincipalName <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The New-ADComputer cmdlet creates a new Active Directory computer object.
This cmdlet does not join a computer to a domain.
You can set commonly used computer property values by using the cmdlet parameters.
Property values that are not associated with cmdlet parameters can be modified by using the OtherAttributes parameter.

You can use this cmdlet to provision a computer account before the computer is added to the domain.
These pre-created computer objects can be used with offline domain join, unsecure domain Join and RODC domain join scenarios.

The Path parameter specifies the container or organizational unit (OU) for the new computer.
When you do not specify the Path parameter, the cmdlet creates a computer account in the default container for computer objects in the domain.

The following methods explain different ways to create an object by using this cmdlet.

Method 1: Use the New-ADComputer cmdlet, specify the required parameters, and set any additional property values by using the cmdlet parameters.

Method 2: Use a template to create the new object.
To do this, create a new computer object or retrieve a copy of an existing computer object and set the Instance parameter to this object.
The object provided to the Instance parameter is used as a template for the new object.
You can override property values from the template by setting cmdlet parameters.
For examples and more information, see the Instance parameter description for this cmdlet.

Method 3: Use the Import-CSV cmdlet with the Add-ADComputer cmdlet to create multiple Active Directory computer objects.
To do this, use the Import-CSV cmdlet to create the custom objects from a comma-separated value (CSV) file that contains a list of object properties.
Then pass these objects through the pipeline to the New-ADComputer cmdlet to create the computer objects.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>New-ADComputer -Name "FABRIKAM-SRV2" -SamAccountName "FABRIKAM-SRV2" -Path "OU=ApplicationServers,OU=ComputerAccounts,OU=Managed,DC=FABRIKAM,DC=COM"
```

Description

-----------

Create a new computer account in the OU: "OU=ApplicationServers,OU=ComputerAccounts,OU=Managed,DC=FABRIKAM,DC=COM".

### -------------------------- EXAMPLE 2 --------------------------
```
C:\PS>New-ADComputer -Name "FABRIKAM-SRV3" -SamAccountName "FABRIKAM-SRV3" -Path "OU=ApplicationServers,OU=ComputerAccounts,OU=Managed,DC=FABRIKAM,DC=COM" -Enabled $true -Location "Redmond,WA"
```

Description

-----------

Create a new computer account under a particular OU, which is enabled and located in "Redmond,WA".

### -------------------------- EXAMPLE 3 --------------------------
```
C:\PS>$templateComp = get-adcomputer "LabServer-00" -properties "Location","OperatingSystem","OperatingSystemHotfix","OperatingSystemServicePack","OperatingSystemVersion"; New-ADComputer -Instance $templateComp -Name "LabServer-01"
```

Description

-----------

Creates a new computer account from a template object.

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

$null password is specified - Random password is set and the account is enabled unless it is requested to be disabled

No password is specified - Random password is set and the account is enabled unless it is requested to be disabled

User password is specified - Password is set and the account is enabled unless it is requested to be disabled, unless the password you provided does not meet password policy or was not set for other reasons, at which point the account is disabled

Notes:  Computer accounts, by default, are created with a 240-character random password.
If you provide a password, an attempt will be made to set that password however, this can fail due to password policy restrictions.
The computer account will still be created and you can use Set-ADAccountPassword to set the password on that account.
In order to ensure that accounts remain secure, computer accounts will never be enabled unless a valid password is set (either a randomly-generated or user-provided one) or PasswordNotRequired is set to true.

The account is created if the password fails for any reason.

The new ADComputer object will always either be disabled or have a user-requested or randomly-generated password.
There is no way to create an enabled computer account object with a password that violates domain password policy, such as an empty password.

The following example shows how to set this parameter.
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
Modifies the DER-encoded X.509v3 certificates of the account.
These certificates include the public key certificates issued to this account by the Microsoft Certificate Service.
This parameter sets the Certificates property of the account object.
The LDAP Display Name (ldapDisplayName) for this property is "userCertificate".

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

### -DNSHostName
Specifies the fully qualified domain name (FQDN) of the computer.
This parameter sets the DNSHostName property for a computer object.
The LDAP Display Name for this property is "dNSHostName".

The following example shows how to set this parameter to a FQDN.

-DNSHostName "corp.contoso.com"

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

### -Instance
Specifies an instance of a computer object to use as a template for a new computer object.

You can use an instance of an existing computer object as a template or you can construct a new computer object by using the Windows PowerShell command line or by using a script.
The following examples show how to use these two methods to create computer object templates.

Method 1: Use an existing computer object as a template for a new object.
To retrieve an instance of an existing computer object use  Get-ADcomputer.
Then provide this object to the Instance parameter of the New-ADcomputer cmdlet to create a new computer object.
You can override property values of the new object by setting the appropriate parameters.

$computerInstance = Get-ADcomputer -Identity ellenAdamsDesktop

New-ADcomputer -Name "saraDavisDesktop"  -Instance $computerInstance -AccountPassword "MustChange242"

-samAccountName "saraDavisDesktop"

Method 2: Create a new ADcomputer object and set the property values by using the Windows PowerShell command line interface.
Then pass this object to the Instance parameter of the New-ADcomputer cmdlet to create the new Active Directory computer object.

$computerInstance = new-object Microsoft.ActiveDirectory.Management.ADcomputer

New-ADcomputer -Name "saraDavisDesktop"  -Instance $computerInstance

Note: Specified attributes are not validated, so attempting to set attributes that do not exist or cannot be set will raise an error.

```yaml
Type: ADComputer
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

None, will remove all encryption types from the account which may result in the KDC being unable to issue service tickets for services using the account.

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

### -Location
Specifies the location of the computer, such as an office number.
This parameter sets the Location property of a computer.
The LDAP display name (ldapDisplayName) of this property is "location".

The following example shows how to set this parameter.

-Location  "Test Lab A"

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

### -OperatingSystem
Specifies an operating system name.
This parameter sets the OperatingSystem property of the computer object.
The LDAP Display Name (ldapDisplayName) for this property is "operatingSystem".

The following example shows how to set this parameter.

-OperatingSystem "Windows Server 2008 Enterprise"

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

### -OperatingSystemHotfix
Specifies an operating system hotfix name.
This parameter sets the operatingSystemHotfix property of the computer object.
The LDAP display name for this property is "operatingSystemHotfix".

The following example shows how to specify this parameter.

-operatingSystemHotfix "523466"

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

### -OperatingSystemServicePack
Specifies the name of an operating system service pack.
This parameter sets the OperatingSystemServicePack property of the computer object.
The LDAP display name (ldapDisplayName) for this property is "operatingSystemServicePack".

The following example shows how to specify this parameter.

-OperatingSystemServicePack "Service Pack 2"

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

### -OperatingSystemVersion
Specifies an operating system version.
This parameter sets the OperatingSystemVersion property of the computer object.
The LDAP display name (ldapDisplayName) for this property is "operatingSystemVersion".

The following example shows how to specify this parameter.

-OperatingSystemVersion "6.0 (6001)"

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
This parameter sets the PasswordNotRequired property of an account, such as a user or computer account.
This parameter also sets the ADS_UF_PASSWD_NOTREQD flag of the Active Directory User Account Control attribute.
Possible values for this parameter are:

$false or 0

$true or 1

The following example shows how to set this parameter so that as password is not required for the account.

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

### -PrincipalsAllowedToDelegateToAccount
Specifies the accounts which can act on the behalf of users to services running as this computer account.
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

### -SAMAccountName
Specifies the Security Account Manager (SAM) account name of the user, group, computer, or service account.
The maximum length of the description is 256 characters.
To be compatible with older operating systems, create a SAM account name that is 15 characters or less.
This parameter sets the SAMAccountName for an account object.
The LDAP display name (ldapDisplayName) for this property is "sAMAccountName".

The following example shows how to specify this parameter.

-SAMAccountName "saradavis"

Note: If the SAMAccountName string provided, does not end with a '$', one will be appended if needed.

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

### None or Microsoft.ActiveDirectory.Management.ADComputer
A computer object that is a template for the new computer object is received by the Instance parameter.

## OUTPUTS

### None or Microsoft.ActiveDirectory.Management.ADComputer
Returns the new computer object when the PassThru parameter is specified.
By default, this cmdlet does not generate any output.

## NOTES
* This cmdlet does not work with AD LDS.

  This cmdlet does not work with an Active Directory Snapshot.

  This cmdlet does not work with a read-only domain controller.

## RELATED LINKS

[Add-ADComputerServiceAccount](./Add-ADComputerServiceAccount.md)

[Get-ADComputer](./Get-ADComputer.md)

[Get-ADComputerServiceAccount](./Get-ADComputerServiceAccount.md)

[Remove-ADComputer](./Remove-ADComputer.md)

[Remove-ADComputerServiceAccount](./Remove-ADComputerServiceAccount.md)

[Set-ADComputer](./Set-ADComputer.md)

