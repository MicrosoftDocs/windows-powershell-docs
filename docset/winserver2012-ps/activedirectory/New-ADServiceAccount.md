---
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
ms.assetid: 488C5812-CD3B-442E-8A66-307C3D383353
manager: dansimp
online version:
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# New-ADServiceAccount

## SYNOPSIS
Creates a new Active Directory managed service account or group managed service account object.

## SYNTAX

### Group (Default)
```yaml
New-ADServiceAccount [-WhatIf] [-Confirm] [-AccountExpirationDate <DateTime>] [-AccountNotDelegated <Boolean>]
 [-AuthType <ADAuthType>] [-Certificates <String[]>] [-CompoundIdentitySupported <Boolean>]
 [-Credential <PSCredential>] [-Description <String>] [-DisplayName <String>] -DNSHostName <String>
 [-Enabled <Boolean>] [-HomePage <String>] [-Instance <ADServiceAccount>]
 [-KerberosEncryptionType <ADKerberosEncryptionType>] [-ManagedPasswordIntervalInDays <Int32>] [-Name] <String>
 [-OtherAttributes <Hashtable>] [-PassThru] [-Path <String>]
 [-PrincipalsAllowedToDelegateToAccount <ADPrincipal[]>]
 [-PrincipalsAllowedToRetrieveManagedPassword <ADPrincipal[]>] [-SamAccountName <String>] [-Server <String>]
 [-ServicePrincipalNames <String[]>] [-TrustedForDelegation <Boolean>] [<CommonParameters>]
```

### RestrictedToSingleComputer
```yaml
New-ADServiceAccount [-WhatIf] [-Confirm] [-AccountExpirationDate <DateTime>] [-AccountNotDelegated <Boolean>]
 [-AccountPassword <SecureString>] [-AuthType <ADAuthType>] [-Certificates <String[]>]
 [-Credential <PSCredential>] [-Description <String>] [-DisplayName <String>] [-Enabled <Boolean>]
 [-HomePage <String>] [-Instance <ADServiceAccount>] [-KerberosEncryptionType <ADKerberosEncryptionType>]
 [-Name] <String> [-OtherAttributes <Hashtable>] [-PassThru] [-Path <String>] [-RestrictToSingleComputer]
 [-SamAccountName <String>] [-Server <String>] [-ServicePrincipalNames <String[]>]
 [-TrustedForDelegation <Boolean>] [<CommonParameters>]
```

### RestrictedToOutboundAuthenticationOnly
```yaml
New-ADServiceAccount [-WhatIf] [-Confirm] [-AccountExpirationDate <DateTime>] [-AccountNotDelegated <Boolean>]
 [-AuthType <ADAuthType>] [-Certificates <String[]>] [-Credential <PSCredential>] [-Description <String>]
 [-DisplayName <String>] [-Enabled <Boolean>] [-HomePage <String>] [-Instance <ADServiceAccount>]
 [-KerberosEncryptionType <ADKerberosEncryptionType>] [-Name] <String> [-OtherAttributes <Hashtable>]
 [-PassThru] [-Path <String>] [-RestrictToOutboundAuthenticationOnly] [-SamAccountName <String>]
 [-Server <String>] [-ServicePrincipalNames <String[]>] [-TrustedForDelegation <Boolean>] [<CommonParameters>]
```

## DESCRIPTION
The New-ADServiceAccount cmdlet creates a new Active Directory managed service account (MSA).
By default a group MSA is created.
To create a standalone MSA which is linked to a specific computer, the -RestrictToSingleComputer parameter is used.
To create a group MSA which can only be used in client roles, the -Agent parameter is used.
This creates a group MSA which can be used for outbound connections only and attempts to connect to services using this account will fail since the account does not have enough information for authentication to be successful.
You can set commonly used MSA property values by using the cmdlet parameters.
Property values that are not associated with cmdlet parameters can be set by using the OtherAttributes parameter.

The Path parameter specifies the container or organizational unit (OU) for the new MSA object.
When you do not specify the Path parameter, the cmdlet creates an object in the default Managed Service Accounts container for MSA objects in the domain.

The following methods explain different ways to create an object by using this cmdlet.

Method 1: Use the New-ADServiceAccount cmdlet, specify the required parameters, and set any additional property values by using the cmdlet parameters.

Method 2: Use a template to create the new object.
To do this, create a new MSA object or retrieve a copy of an existing MSA object and set the Instance parameter to this object.
The object provided to the Instance parameter is used as a template for the new object.
You can override property values from the template by setting cmdlet parameters.
For examples and more information, see the Instance parameter description for this cmdlet.

Method 3: Use the Import-CSV cmdlet with the New-ADServiceAccount cmdlet to create multiple Active Directory MSA objects.
To do this, use the Import-CSV cmdlet to create the custom objects from a comma-separated value (CSV) file that contains a list of object properties.
Then pass these objects through the pipeline to the New-ADServiceAccount cmdlet to create the MSA objects.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
Create a new enabled managed service account in AD DS.

```Powershell
C:\PS>New-ADServiceAccount service1 -DNSHostName service1.contoso.com -Enabled $true
```

### -------------------------- EXAMPLE 2 --------------------------
Create a new managed service account and register its service principal name.

```Powershell
C:\PS>New-ADServiceAccount service1 -ServicePrincipalNames "MSSQLSVC/Machine3.corp.contoso.com" -DNSHostName service1.contoso.com
```

### -------------------------- EXAMPLE 3 --------------------------
Create a new managed service account and restrict its use to only a single computer.

```Powershell
C:\PS>New-ADServiceAccount service1 -RestrictToSingleComputer
```

### -------------------------- EXAMPLE 4 --------------------------
Create a new managed service account and restrict its use to only outbound authentication.

```Powershell
C:\PS>New-ADServiceAccount service1 -RestrictToOutboundAuthenticationOnly
```

### -------------------------- EXAMPLE 5 --------------------------
Create a new managed service account and register multiple service principal names.

```Powershell
C:\PS>New-ADServiceAccount service1 -ServicePrincipalNames "HTTP/Machine3.corp.contoso.com,HTTP/Machine3.corp.contoso.com/contoso" -DNSHostName service1.contoso.com
```

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
`"4/17/2006"`

`"Monday, April 17, 2006"`

`"2:22:45 PM"`

`"Monday, April 17, 2006 2:22:45 PM"`

These examples specify the same date and the time without the seconds.


`"4/17/2006 2:22 PM"`

`"Monday, April 17, 2006 2:22 PM"`

`"2:22 PM"`


The following example shows how to specify a date and time by using the RFC1123 standard.
This example defines time by using Greenwich Mean Time (GMT).

`"Mon, 17 Apr 2006 21:22:48 GMT"`

The following example shows how to specify a round-trip value as Coordinated Universal Time (UTC).
This example represents Monday, April 17, 2006 at 2:22:48 PM UTC.

`"2006-04-17T14:22:48.0000000"`

The following example shows how to set this parameter to the date May 1, 2012 at 5 PM.

`-AccountExpirationDate "05/01/2012 5:00:00 PM"`

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
```Powershell
-AccountNotDelegated $true
```
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
Specifies a new password value for the service account.
This value is stored as an encrypted string.

The following conditions apply based on the manner in which the password parameter is used:

$null password is specified - Random password is set and the account is enabled unless it is requested to be disabled

No password is specified - Random password is set and the account is enabled unless it is requested to be disabled

User password is specified - Password is set and the account is enabled unless it is requested to be disabled, unless the password you provided does not meet password policy or was not set for other reasons, at which point the account is disabled

The new ADServiceAccount object will always either be disabled or have a user-requested or randomly-generated password.
There is no way to create an enabled service account object with a password that violates domain password policy, such as an empty password.

The following example shows how to set this parameter.
This command will prompt you to enter the password.
```Powershell
-AccountPassword (Read-Host -AsSecureString "AccountPassword")
```
```yaml
Type: SecureString
Parameter Sets: RestrictedToSingleComputer
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
```Powershell
-AuthType Basic
```
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

### -Certificates
Modifies the DER-encoded X.509v3 certificates of the account.
These certificates include the public key certificates issued to this account by the Microsoft Certificate Service.
This parameter sets the Certificates property of the account object.
The LDAP Display Name (ldapDisplayName) for this property is "userCertificate".

Syntax:

To add values:
```Powershell
-Certificates @{Add=value1,value2,...}
```
To remove values:
```Powershell
-Certificates @{Remove=value3,value4,...}
```
To replace values:
```Powershell
-Certificates @{Replace=value1,value2,...}
```
To clear all values:
```Powershell
-Certificates $null
```
You can specify more than one operation by using a list separated by semicolons.
For example, use the following syntax to add and remove Certificate values
```Powershell
-Certificates @{Add=value1,value2,...};@{Remove=value3,value4,...}
```
The operators will be applied in the following sequence:

- Remove
- Add
- Replace

The following example shows how to create a certificate by using the New-Object cmdlet, and then add it to a user account.
When this cmdlet is run, \<certificate password\> is replaced by the password used to add the certificate.
```Powershell
$cert = New-Object System.Security.Cryptography.X509Certificates.X509Certificate certificate1.cer  \<certificate password\>

Set-ADServiceAccount Service1  -Certificates @{Add=$cert}
```
The following example shows how to add a certificate that is specified as a byte array.
```Powershell
Set-ADServiceAccount Service1  -Certificates @{Add= \[Byte\[\]\](0xC5,0xEE,0x53,...)}
```
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

### -CompoundIdentitySupported
Specifies whether an account supports Kerberos service tickets which includes the authorization data for the user's device.
This value sets the compound identity supported flag of the Active Directory msDS-SupportedEncryptionTypes attribute.
Possible values for this parameter are:

$false or 0

$true or 1

The following example shows how to specify that an account supports compound identity.
```Powershell
-CompoundIdentitySupported $true
```
Warning: Domain-joined Windows systems and services such as clustering manage their own msDS-SupportedEncryptionTypes attribute.
Therefore any changes to the flag on the msDS-SupportedEncryptionTypes attribute will be overwritten by the service or system which manages the setting.

```yaml
Type: Boolean
Parameter Sets: Group
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
Specifies the service account credentials to use to perform this task.
The default credentials are the credentials of the currently logged on user unless the cmdlet is run from an Active Directory PowerShell provider drive.
If the cmdlet is run from such a provider drive, the account associated with the drive is the default.

To specify this parameter, you can type an administrative account name, such as "Admin1" or "Contoso\Admin1" or you can specify a PSCredential object.
If you specify a service account name for this parameter, the cmdlet prompts for a password.

You can also create a PSCredential object by using a script or by using the Get-Credential cmdlet.
You can then use it to specify the Credential parameter to the ADServiceAccount object.

The following example shows how to create credentials.
```Powershell
$AdminCredentials = Get-Credential "Contoso\Admin1"
```
The following shows how to use the PSCredential object to specify administrative credentials when creating a new ADServiceAccount object by using the Credential parameter.
```Powershell
New-ADServiceAccount -Credential $AdminCredentials
```
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
Specifies the DNS (Domain Name System) host name of the Service Account.

This parameter sets the value of the FQDN (Fully Qualified Domain Name) for the Service Account created.

The following example shows how to set this parameter for a Service Account called service1 in the domain contoso.com
```Powershell
-DNSHostName service1.contoso.com
```

```yaml
Type: String
Parameter Sets: Group
Aliases:

Required: True
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
```Powershell
-Description "Description of the object"
```
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

The following example shows how to include this parameter when creating a new service account.
```Powershell
New-ADServiceAccount -DisplayName "Service Account for use with Contoso LOB Application"
```
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

The following example shows how to set this parameter to enable the service account when creating it.
```Powershell
New-ADServiceAccount -Enabled $true
```
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

The following example shows how to set this parameter to a URL when creating the service account.
```Powershell
New-ADServiceAccount -HomePage "http://accounts.contoso.com/Service1"
```
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
Specifies an instance of a service account object to use as a template for a new service account object.

You can use an instance of an existing service account object as a template or you can construct a new service account object for template use.
You can construct a new service account using the Windows PowerShell command line or by using a script.
The following examples show how to use these two methods to create service account object templates.

Method 1: Use an existing service account object as a template for a new object.
To retrieve an instance of an existing service account object, use a cmdlet such as Get-ADServiceAccount.
Then provide this object to the Instance parameter of the New-ADServiceAccount cmdlet to create a new service account object.
You can override property values of the new object by setting the appropriate parameters.
```Powershell
$serviceAccountInstance = Get-ADServiceAccount -Identity

New-ADServiceAccount -Name "ServiceAdmin2" -Instance $serviceAccountInstance   -Description "Service Account 2"
```
Method 2: Create a new ADServiceAccount object and set the property values by using the Windows PowerShell command line interface.
Then pass this object to the Instance parameter of the New-ADServiceAccount cmdlet to create the new Active Directory service account object.
```Powershell
$serviceAccountInstance = new-object Microsoft.ActiveDirectory.Management.ADServiceAccount

$serviceAccountInstance.
Description "Service Account 2"
```
Note: Specified attributes are not validated, so attempting to set attributes that do not exist or cannot be set will raise an error.

```yaml
Type: ADServiceAccount
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

None, will remove all encryption types from the account may result in the KDC being unable to issue service tickets for services using the account.

DES is a weak encryption type which is not supported by default since Windows 7 and Windows Server 2008 R2.

The following example shows how to specify that an account supports service tickets with device authorization data.
```Powershell
-KerberosEncryptionTypes RC4,AES128,AES256
```
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
Accept pipeline input: False
Accept wildcard characters: False
```

### -ManagedPasswordIntervalInDays
Specifies the number of days for the password change interval.
If set to 0 then the default is used.
This can only be set on object creation.
After that the setting is read only.
This value returns the msDS-ManagedPasswordInterval of the group managed service account object.

The following example shows how to specify a 90 day password changes interval:
```Powershell
-ManagedPasswordIntervalInDays 90
```
```yaml
Type: Int32
Parameter Sets: Group
Aliases:

Required: False
Position: Named
Default value: 30
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of the object.
This parameter sets the Name property of the Active Directory object.
The LDAP Display Name (ldapDisplayName) of this property is "name".

The following example shows how to set this parameter to a name string.
```Powershell
-Name "Service1"
```
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

### -OtherAttributes
Specifies object attribute values for attributes that are not represented by cmdlet parameters.
You can set one or more parameters at the same time with this parameter.
If an attribute takes more than one value, you can assign multiple values.
To identify an attribute, specify the LDAPDisplayName (ldapDisplayName) defined for it in the Active Directory schema.

Syntax:

To specify a single value for an attribute:
```Powershell
-OtherAttributes @{'AttributeLDAPDisplayName'=value}
```
To specify multiple values for an attribute
```Powershell
-OtherAttributes @{'AttributeLDAPDisplayName'=value1,value2,...}
```
You can specify values for more than one attribute by using semicolons to separate attributes.
The following syntax shows how to set values for multiple attributes:
```Powershell
-OtherAttributes @{'Attribute1LDAPDisplayName'=value; 'Attribute2LDAPDisplayName'=value1,value2;...}
```
The following examples show how to use this parameter.

To set the value of a custom attribute called favColors that takes a set of Unicode strings, use the following syntax:
```Powershell
-OtherAttributes @{'favColors'="pink","purple"}
```
To set values for favColors and dateOfBirth simultaneously, use the following syntax:
```Powershell
-OtherAttributes @{'favColors'="pink","purple"; 'dateOfBirth'=" 01/01/1960"}
```
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

### -Path
Specifies the X.500 path of the Organizational Unit (OU) or container where the new object is created.

In many cases, a default value will be used for the Path parameter if no value is specified.
The rules for determining the default value are given below.
Note that rules listed first are evaluated first and once a default value can be determined, no further rules will be evaluated.

In AD DS environments, a default value for Path will be set in the following cases:

- If the cmdlet is run from an Active Directory PowerShell provider drive, the parameter is set to the current path of the provider drive.
- If the cmdlet has a default path, this will be used. For example: in New-ADUser, the Path parameter would default to the Users container.
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
Specifies the accounts which can act on the behalf of users to services running as this Managed Service Account or Group Managed Service Account.
This parameter sets the msDS-AllowedToActOnBehalfOfOtherIdentity attribute of the object.

```yaml
Type: ADPrincipal[]
Parameter Sets: Group
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PrincipalsAllowedToRetrieveManagedPassword
Specifies the membership policy for systems which can use a group managed service account.
For a service to run under a group managed service account, the system must be in the membership policy of the account.
This parameter sets the msDS-GroupMSAMembership attribute of a group managed service account object.
This parameter should be set to the principals allowed to use this group managed service account.

```yaml
Type: ADPrincipal[]
Parameter Sets: Group
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RestrictToOutboundAuthenticationOnly
Switch which is used to create a group managed service account which on success can be used by a service for successful outbound authentication requests only.
This allows creating a group managed service account without the parameters required for successful inbound authentication.

```yaml
Type: SwitchParameter
Parameter Sets: RestrictedToOutboundAuthenticationOnly
Aliases:
Accepted values: true

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RestrictToSingleComputer
Switch which is used to create a managed service account that can be used only for a single computer.
These managed service accounts which are linked to a single computer account were introduced in Windows Server 2008 R2.

```yaml
Type: SwitchParameter
Parameter Sets: RestrictedToSingleComputer
Aliases:
Accepted values: true

Required: True
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
```Powershell
-SAMAccountName "Service1"
```
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

Fully qualified domain name (FQDN)

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
```Powershell
New-ADServiceAccount -Server "corp.contoso.com"
```
The following example shows how to specify a full qualified directory server name as the parameter value.
```Powershell
New-ADServiceAccount -Server "corp-DC12.corp.contoso.com"
```
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
This parameter sets the **ServicePrincipalNames** property of the account.
The LDAP display name (**ldapDisplayName**) for this property is servicePrincipalName.
This parameter can be used to set multiple Service Principal Names, specifying each one separated with commas.

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
 ```Powershell
-TrustedForDelegation $true
 ```
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

### None or Microsoft.ActiveDirectory.Management.ADServiceAccount
A managed service account object that is a template for the new managed service account object is received by the Instance parameter.

## OUTPUTS

### None or Microsoft.ActiveDirectory.Management.ADServiceAccount
Returns the new managed service account object when the PassThru parameter is specified.
By default, this cmdlet does not generate any output.

## NOTES
* This cmdlet does not work with AD LDS.

  This cmdlet does not work with an Active Directory Snapshot.

  This cmdlet does not work with a read-only domain controller.

  This cmdlet requires that you create a Microsoft Key Distribution Service root key first to begin using group managed service accounts in your Active Directory deployment.
For more information on how to create the KDS root key using Windows PowerShell, see Create the Key Distribution Services KDS Root Keyhttp://go.microsoft.com/fwlink/?LinkId=253584 (http://go.microsoft.com/fwlink/?LinkId=253584).

## RELATED LINKS

[Get-ADServiceAccount](./Get-ADServiceAccount.md)

[Install-ADServiceAccount](./Install-ADServiceAccount.md)

[Remove-ADServiceAccount](./Remove-ADServiceAccount.md)

[Set-ADServiceAccount](./Set-ADServiceAccount.md)

[Uninstall-ADServiceAccount](./Uninstall-ADServiceAccount.md)
