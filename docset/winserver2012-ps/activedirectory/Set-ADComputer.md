---
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
online version: https://docs.microsoft.com/powershell/module/activedirectory/set-adcomputer?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-ADComputer

## SYNOPSIS
Modifies an Active Directory computer object.

## SYNTAX

### Identity
```
Set-ADComputer [-WhatIf] [-Confirm] [-AccountExpirationDate <DateTime>] [-AccountNotDelegated <Boolean>]
 [-Add <Hashtable>] [-AllowReversiblePasswordEncryption <Boolean>] [-AuthType <ADAuthType>]
 [-CannotChangePassword <Boolean>] [-Certificates <Hashtable>] [-ChangePasswordAtLogon <Boolean>]
 [-Clear <String[]>] [-CompoundIdentitySupported <Boolean>] [-Credential <PSCredential>]
 [-Description <String>] [-DisplayName <String>] [-DNSHostName <String>] [-Enabled <Boolean>]
 [-HomePage <String>] [-Identity] <ADComputer> [-KerberosEncryptionType <ADKerberosEncryptionType>]
 [-Location <String>] [-ManagedBy <ADPrincipal>] [-OperatingSystem <String>] [-OperatingSystemHotfix <String>]
 [-OperatingSystemServicePack <String>] [-OperatingSystemVersion <String>] [-Partition <String>] [-PassThru]
 [-PasswordNeverExpires <Boolean>] [-PasswordNotRequired <Boolean>]
 [-PrincipalsAllowedToDelegateToAccount <ADPrincipal[]>] [-Remove <Hashtable>] [-Replace <Hashtable>]
 [-SAMAccountName <String>] [-Server <String>] [-ServicePrincipalNames <Hashtable>]
 [-TrustedForDelegation <Boolean>] [-UserPrincipalName <String>] [<CommonParameters>]
```

### Instance
```
Set-ADComputer [-WhatIf] [-Confirm] [-AuthType <ADAuthType>] [-Credential <PSCredential>]
 -Instance <ADComputer> [-PassThru] [-Server <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-ADComputer** cmdlet modifies the properties of an Active Directory computer object.
You can modify commonly used property values by using the cmdlet parameters.
Property values that are not associated with cmdlet parameters can be modified by using the *Add*, *Replace*, *Clear*, and *Remove* parameters.

The *Identity* parameter specifies the Active Directory computer to modify.
You can identify a computer by its distinguished name, GUID, security identifier (SID), or Security Accounts Manager (SAM) account name.
You can also set the *Identity* parameter to an object variable such as `$<localComputerobject>`, or you can pass an object through the pipeline to the *Identity* parameter.
For example, you can use the **Get-ADComputer** cmdlet to retrieve a computer object and then pass the object through the pipeline to Set-ADComputer.

The *Instance* parameter provides a way to update a computer by applying the changes made to a copy of the computer object.
When you set the *Instance* parameter to a copy of an Active Directory computer object that has been modified, the **Set-ADComputer** cmdlet makes the same changes to the original computer object.
To get a copy of the object to modify, use the Get-ADComputer object.
When you specify the *Instance* parameter you should not pass the *Identity* parameter.
For more information about the *Instance* parameter, see the *Instance* parameter description.

## EXAMPLES

### Example 1: Modify the SPN value for a specified Active Directory computer
```
PS C:\> Set-ADComputer -Identity "USER01-SRV1" -ServicePrincipalName @{Replace="MSSQLSVC/USER01-SRV1.USER01.COM:1456","MSOLAPSVC.3/USER01-SRV1.USER01.COM:analyze"}
```

This command modifies the service principal name (SPN) value for the computer specified by the *Identity* parameter.

### Example 2: Set the location for a specified Active Directory computer
```
PS C:\> Set-ADComputer -Identity "USER02-SRV1" -Location "NA/HQ/Building A"
```

This command sets the location for the computer specified by the *Identity* parameter.

### Example 3: Set an attribute for a specified Active Directory computer using a SAM account name
```
PS C:\> Set-ADComputer -Identity "USER03-SRV1" -ManagedBy "CN=SQL Administrator 01,OU=UserAccounts,OU=Managed,DC=USER03,DC=COM"
```

This command sets the **ManagedBy** attribute value for the computer specified by the *Identity* parameter using the SAM account name of the user.

### Example 4: Set multiple attributes of an Active Directory computer
```
PS C:\> $Comp = Get-ADComputer -Identity "USER04-SRV1" 
PS C:\> $Comp.Location = "NA/HQ/Building A" 
PS C:\> $Comp.ManagedBy = "CN=SQL Administrator 01,OU=UserAccounts,OU=Managed,DC=USER04,DC=COM" 
PS C:\> Set-ADComputer -Instance $Comp
```

This command sets the **Location** and **ManagedBy**  attributes of a computer.

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

-Certificates @{Add=value1,value2,...;Remove=value3,value4,...}

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

### -Instance
Specifies a modified copy of a computer object to use to update the actual Active Directory computer object.
When this parameter is used, any modifications made to the modified copy of the object are also made to the corresponding Active Directory object.
The cmdlet only updates the object properties that have changed.

The Instance parameter can only update computer objects that have been retrieved by using the Get-ADComputer cmdlet.
When you specify the Instance parameter, you cannot specify other parameters that set properties on the object.

The following is an example of how to use the Get-ADComputer cmdlet to retrieve an instance of the ADComputer object.
The object is modified by using the Windows PowerShell command line.
Then the Set-ADComputer cmdlet saves the changes to the Active Directory object.

Step 1: Retrieve a local instance of the object.

$computerInstance = Get-ADComputer  -Identity saraDavisDesktop

Step 2: Modify one or more properties of the object instance.

$computerInstance.Description = "Sara Davis Computer"

Step3: Save your changes to saraDavisDesktop.

Set-ADComputer -Instance $computerInstance

```yaml
Type: ADComputer
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

None, will remove all encryption types from the account which may result in the KDC being unable to issue service tickets for services using the account.

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

### -Location
Specifies the location of the computer, such as an office number.
This parameter sets the Location property of a computer.
The LDAP display name (ldapDisplayName) of this property is "location".

The following example shows how to set this parameter.

-Location  "Test Lab A"

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
Parameter Sets: Identity
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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
Parameter Sets: Identity
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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
Parameter Sets: Identity
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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
Parameter Sets: Identity
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

### -PrincipalsAllowedToDelegateToAccount
Specifies the accounts which can act on the behalf of users to services running as this computer account.
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
You can specify multiple values to a property by specifying a comma-separated list of values, and more than one property by separating them using a semicolon.
The format for this parameter is:

`-Replace @{Attribute1LDAPDisplayName=value1, value2, ...;   Attribute2LDAPDisplayName=value1, value2, ...; AttributeNLDAPDisplayName=value1, value2, ...}`

When you use the *Add*, *Remove*, *Replace*, and *Clear* parameters together, the operations will be performed in the following order:

- **Remove**
- **Add**
- **Replace**
- **Clear**

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

### -SAMAccountName
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

@{Add=value1,value2,...;Remove=value3,value4,...}

The operators will be applied in the following sequence:

..Remove

..Add

..Replace

The following example shows how to add and remove service principal names.

-ServicePrincipalNames-@{Add="SQLservice\accounting.corp.contoso.com:1456";Remove="SQLservice\finance.corp.contoso.com:1456"}

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.ActiveDirectory.Management.ADComputer
A computer object is received by the Identity parameter.

A computer object that was retrieved by using the Get-ADComputer cmdlet and then modified is received by the Instance parameter.

## OUTPUTS

### None or Microsoft.ActiveDirectory.Management.ADComputer
Returns the modified computer object when the PassThru parameter is specified.
By default, this cmdlet does not generate any output.

## NOTES
* This cmdlet does not work with AD LDS.

  This cmdlet does not work with an Active Directory Snapshot.

  This cmdlet does not work with a read-only domain controller.

  This cmdlet does not work when connected to Global Catalog port.

## RELATED LINKS

[Add-ADComputerServiceAccount](./Add-ADComputerServiceAccount.md)

[Get-ADComputer](./Get-ADComputer.md)

[Get-ADComputerServiceAccount](./Get-ADComputerServiceAccount.md)

[New-ADComputer](./New-ADComputer.md)

[Remove-ADComputer](./Remove-ADComputer.md)

[Remove-ADComputerServiceAccount](./Remove-ADComputerServiceAccount.md)
