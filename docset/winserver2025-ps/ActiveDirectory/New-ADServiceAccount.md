---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
ms.date: 02/15/2024
online version: https://learn.microsoft.com/powershell/module/activedirectory/new-adserviceaccount?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-ADServiceAccount
---

# New-ADServiceAccount

## SYNOPSIS
Creates a new Active Directory managed service account or group managed service account object.

## SYNTAX

### Group (Default)

```
New-ADServiceAccount [-WhatIf] [-Confirm] [-AccountExpirationDate <DateTime>]
 [-AccountNotDelegated <Boolean>] [-AuthenticationPolicy <ADAuthenticationPolicy>]
 [-AuthenticationPolicySilo <ADAuthenticationPolicySilo>] [-AuthType <ADAuthType>]
 [-Certificates <String[]>] [-CompoundIdentitySupported <Boolean>] [-Credential <PSCredential>]
 [-Description <String>] [-DisplayName <String>] -DNSHostName <String> [-Enabled <Boolean>]
 [-HomePage <String>] [-Instance <ADServiceAccount>]
 [-KerberosEncryptionType <ADKerberosEncryptionType>] [-ManagedPasswordIntervalInDays <Int32>]
 [-Name] <String> [-OtherAttributes <Hashtable>] [-PassThru] [-Path <String>]
 [-CreateDelegatedServiceAccount] [-PrincipalsAllowedToDelegateToAccount <ADPrincipal[]>]
 [-PrincipalsAllowedToRetrieveManagedPassword <ADPrincipal[]>] [-SamAccountName <String>]
 [-Server <String>] [-ServicePrincipalNames <String[]>] [-TrustedForDelegation <Boolean>]
 [<CommonParameters>]
```

### RestrictedToSingleComputer

```
New-ADServiceAccount [-WhatIf] [-Confirm] [-AccountExpirationDate <DateTime>]
 [-AccountNotDelegated <Boolean>] [-AccountPassword <SecureString>]
 [-AuthenticationPolicy <ADAuthenticationPolicy>]
 [-AuthenticationPolicySilo <ADAuthenticationPolicySilo>] [-AuthType <ADAuthType>]
 [-Certificates <String[]>] [-Credential <PSCredential>] [-Description <String>]
 [-DisplayName <String>] [-Enabled <Boolean>] [-HomePage <String>] [-Instance <ADServiceAccount>]
 [-KerberosEncryptionType <ADKerberosEncryptionType>] [-Name] <String>
 [-OtherAttributes <Hashtable>] [-PassThru] [-Path <String>] [-RestrictToSingleComputer]
 [-SamAccountName <String>] [-Server <String>] [-ServicePrincipalNames <String[]>]
 [-TrustedForDelegation <Boolean>] [<CommonParameters>]
```

### RestrictedToOutboundAuthenticationOnly

```
New-ADServiceAccount [-WhatIf] [-Confirm] [-AccountExpirationDate <DateTime>]
 [-AccountNotDelegated <Boolean>] [-AuthenticationPolicy <ADAuthenticationPolicy>]
 [-AuthenticationPolicySilo <ADAuthenticationPolicySilo>] [-AuthType <ADAuthType>]
 [-Certificates <String[]>] [-Credential <PSCredential>] [-Description <String>]
 [-DisplayName <String>] [-Enabled <Boolean>] [-HomePage <String>] [-Instance <ADServiceAccount>]
 [-KerberosEncryptionType <ADKerberosEncryptionType>] [-Name] <String>
 [-OtherAttributes <Hashtable>] [-PassThru] [-Path <String>]
 [-RestrictToOutboundAuthenticationOnly] [-SamAccountName <String>] [-Server <String>]
 [-ServicePrincipalNames <String[]>] [-TrustedForDelegation <Boolean>] [<CommonParameters>]
```

## DESCRIPTION

The `New-ADServiceAccount` cmdlet creates a new Active Directory managed service account. By
default, the cmdlet creates a group managed service account. To create a delegated managed service
account, use the **CreateDelegatedServiceAccount** parameter. Delegated managed service accounts
can be used to migrate services that use normal user accounts. To create a standalone managed
service account which is linked to a specific computer, use the **RestrictToSingleComputer**
parameter. To create a group managed service account which can only be used in client roles, use
the **RestrictToOutboundAuthenticationOnly** parameter. This creates a group managed service
account that can be used for outbound connections only and any attempts to connect to services
using this account will fail because the account doesn't have enough information for
authentication. You can set commonly used managed service account property values by using the
cmdlet parameters. Property values that aren't associated with cmdlet parameters can be set by
using the **OtherAttributes** parameter.

The **Path** parameter specifies the container or organizational unit (OU) for the new managed
service account object. When you Don�t specify the **Path** parameter, the cmdlet creates an
object in the default managed service accounts container for managed service account objects in the
domain.

The following methods explain different ways to create an object by using this cmdlet.

- Method 1: Use the `New-ADServiceAccount` cmdlet, specify the required parameters, and set any
  additional property values by using the cmdlet parameters.

- Method 2: Use a template to create the new object. To do this, create a new managed service
  account object or retrieve a copy of an existing managed service account object and set the
  **Instance** parameter to this object. The object provided to the **Instance** parameter is used
  as a template for the new object. You can override property values from the template by setting
  cmdlet parameters. For examples and more information, see the **Instance** parameter description
  for this cmdlet.

- Method 3: Use the `Import-Csv` cmdlet with the `New-ADServiceAccount` cmdlet to create
  multiple Active Directory managed service account objects. To do this, use the `Import-CSV`
  cmdlet to create the custom objects from a comma-separated value (CSV) file that contains a list
  of object properties. For more information, type `Get-Help Import-CSV`. Then pass these objects
  through the pipeline to the `New-ADServiceAccount` cmdlet to create the managed service account
  objects.

## EXAMPLES

### Example 1: Create an enabled managed service account

```powershell
New-ADServiceAccount -Name "Service01" -DNSHostName "Service01.contoso.com" -Enabled $True
```

This command creates an enabled managed service account in Active Directory Domain Services (AD DS).

### Example 2: Create a managed service account and register its service principal name

```powershell
$params = @{
    Name = "Service01"
    ServicePrincipalNames = "MSSQLSVC/Machine3.corp.contoso.com"
    DNSHostName = "Service01.contoso.com"
}
New-ADServiceAccount @params
```

This command creates a managed service account and registers its service principal name.

### Example 3: Create a managed service account for a single computer

```powershell
New-ADServiceAccount -Name "Service01" -RestrictToSingleComputer
```

This command creates a managed service account and restricts its use to a single computer.

### Example 4: Create a managed service account for outbound authentication only

```powershell
New-ADServiceAccount -Name "Service01" -RestrictToOutboundAuthenticationOnly
```

This command creates a managed service account and restricts its use to outbound authentication.

### Example 5: Create a new managed service account and register multiple service principal names

```powershell
$params = @{
    Name = "Service01"
    ServicePrincipalNames = "HTTP/Machine3.corp.contoso.com","HTTP/Machine3.corp.contoso.com/contoso"
    DNSHostName = "Service01.contoso.com"
}
New-ADServiceAccount @params
```

This command creates a delegated managed service account.

### Example 6: Create an enabled delegated managed service account to be used for migration

```powershell
$params = @{
    Name = "Service01"
    DNSHostName = "Service01.contoso.com"
    Enabled = $True
    CreateDelegatedServiceAccount = $True
}
New-ADServiceAccount @params
```

## PARAMETERS

### -AccountExpirationDate

Specifies the expiration date for an account. This parameter sets the **AccountExpirationDate**
property of an account object. The LDAP display name (**ldapDisplayName**) for this property is
accountExpires.

Use the **DateTime** syntax when you specify this parameter. Time is assumed to be local time
unless otherwise specified. When a time value isn't specified, the time is assumed to 12:00:00 AM
local time. When a date isn't specified, the date is assumed to be the current date.

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

Indicates whether the security context of the user is delegated to a service. When this parameter
is set to true, the security context of the account isn't delegated to a service even when the
service account is set as trusted for Kerberos delegation. This parameter sets the
**AccountNotDelegated** property for an Active Directory account. This parameter also sets the
**ADS_UF_NOT_DELEGATED** flag of the Active Directory User Account Control (UAC) attribute.

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

Specifies a new password value for the service account. This value is stored as an encrypted
string.

The following conditions apply based on the manner in which the password parameter is used:

- $Null password is specified. Random password is set and the account is enabled unless it's
  requested to be disabled.
- No password is specified. Random password is set and the account is enabled unless it's
  requested to be disabled.
- User password is specified. Password is set and the account is enabled unless it's requested to
  be disabled, unless the password you provided doesn't meet password policy or was not set for
  other reasons, at which point the account is disabled.

The new **ADServiceAccount** object will always either be disabled or have a user-requested or
randomly-generated password. there's no way to create an enabled service account object with a
password that violates domain password policy, such as an empty password.

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

### -AuthenticationPolicy

Specifies an Active Directory Domain Services authentication policy object. Specify the
authentication policy object in one of the following formats:

- Distinguished name
- GUID
- Name

This parameter can also get this object through the pipeline or you can set this parameter to an
object instance.

The cmdlet searches the default naming context or partition to find the object. If the cmdlet finds
two or more objects, the cmdlet returns a non-terminating error.

```yaml
Type: ADAuthenticationPolicy
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AuthenticationPolicySilo

Specifies an Active Directory Domain Services authentication policy silo object. Specify the
authentication policy silo object in one of the following formats:

- Distinguished name
- GUID
- Name

This parameter can also get this object through the pipeline or you can set this parameter to an
object instance.

The cmdlet searches the default naming context or partition to find the object. If the cmdlet finds
two or more objects, the cmdlet returns a non-terminating error.

```yaml
Type: ADAuthenticationPolicySilo
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AuthType

Specifies the authentication method to use. The acceptable values for this parameter are:

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

### -Certificates

Specifies an array of certificates. The cmdlet modifies the DER-encoded X.509v3 certificates of the
account. These certificates include the public key certificates issued to this account by the
Microsoft Certificate Service. This parameter sets the **Certificates** property of the account
object. The LDAP Display Name (**ldapDisplayName**) for this property is userCertificate.

To add values:

`-Certificates @{Add=value1,value2,...}`

To remove values:

`-Certificates @{Remove=value3,value4,...}`

To replace values:

`-Certificates @{Replace=value1,value2,...}`

To clear all values:

`-Certificates $Null`

You can specify more than one operation by using a list separated by semicolons. For example, use
the following syntax to add and remove Certificate values:

`-Certificates @{Add=value1,value2,...};@{Remove=value3,value4,...}`

The operators are applied in the following sequence:

- Remove
- Add
- Replace

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

Indicates whether an account supports Kerberos service tickets which includes the authorization
data for the user's device. This value sets the compound identity supported flag of the Active
Directory `msDS-SupportedEncryptionTypes` attribute. The acceptable values for this parameter
are:

- $False or 0
- $True or 1

Warning: Domain-joined Windows systems and services such as clustering manage their own
`msDS-SupportedEncryptionTypes` attribute. Therefore any changes to the flag on the
`msDS-SupportedEncryptionTypes` attribute will be overwritten by the service or system which
manages the setting.

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

Specifies the service account credentials to use to perform this task. The default credentials are
the credentials of the currently logged on user unless the cmdlet is run from an Active Directory
PowerShell provider drive. If the cmdlet is run from such a provider drive, the account associated
with the drive is the default.

To specify this parameter, you can type an administrative account name, such as `Admin1` or
`Contoso\Admin1` or you can specify a **PSCredential** object. If you specify a service account name
for this parameter, the cmdlet prompts for a password.

You can also create a **PSCredential** object by using a script or by using the `Get-Credential`
cmdlet. You can then set the *Credential* parameter to the **PSCredential** object.

If the acting credentials don't have directory-level permission to perform the task, Active
Directory PowerShell returns a terminating error.

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

### -Description

Specifies a description of the object. This parameter sets the value of the **Description**
property for the object. The LDAP Display Name (**ldapDisplayName**) for this property is
description.

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

Specifies the display name of the object. This parameter sets the **DisplayName** property of the
object. The LDAP Display Name (**ldapDisplayName**) for this property is displayName.

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

### -DNSHostName

Specifies the DNS host name of Service Account.

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

### -Enabled

Indicates whether an account is enabled. An enabled account requires a password. This parameter
sets the **Enabled** property for an account object. This parameter also sets the
**ADS_UF_ACCOUNTDISABLE** flag of the Active Directory UAC attribute.

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

Specifies the URL of the home page of the object. This parameter sets the **homePage** property of
an Active Directory object. The LDAP Display Name (**ldapDisplayName**) for this property is
wWWHomePage.

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

Specifies an instance of a service account object to use as a template for a new service account
object.

You can use an instance of an existing service account object as a template or you can construct a
new service account object for template use. You can construct a new service account using the
Windows PowerShell command line or by using a script.

Note: Specified attributes aren't validated, so attempting to set attributes that Don�t exist or
can't be set raises an error.

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

Indicates whether an account supports Kerberos encryption types which are used during creation of
service tickets. This value sets the encryption types supported flags of the Active Directory
`msDS-SupportedEncryptionTypes` attribute. The acceptable values for this parameter are:

- None
- DES
- RC4
- AES128
- AES256

None will remove all encryption types from the account may result in the KDC being unable to issue
service tickets for services using the account.

DES is a weak encryption type that'sn't supported by default since Windows 7 and Windows Server
2008 R2.

Warning: Domain-joined Windows systems and services such as clustering manage their own
`msDS-SupportedEncryptionTypes` attribute. Therefore any changes to the flag on the
`msDS-SupportedEncryptionTypes` attribute will be overwritten by the service or system which
manages the setting.

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

Specifies the number of days for the password change interval. If set to 0 then the default is
used. This can only be set on object creation. After that the setting is read only. This value
returns the `msDS-ManagedPasswordInterval` of the group managed service account object.

```yaml
Type: Int32
Parameter Sets: Group
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name

Specifies the name of the object. This parameter sets the **Name** property of the Active Directory
object. The LDAP Display Name (**ldapDisplayName**) of this property is name.

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

Specifies object attribute values for attributes that aren't represented by cmdlet parameters. You
can set one or more parameters at the same time with this parameter. If an attribute takes more
than one value, you can assign multiple values. To identify an attribute, specify the LDAP Display
Name (**ldapDisplayName**) defined for it in the Active Directory schema.

To specify a single value for an attribute:

`-OtherAttributes @{'AttributeLDAPDisplayName'=value}`

To specify multiple values for an attribute

`-OtherAttributes @{'AttributeLDAPDisplayName'=value1,value2,...}`

You can specify values for more than one attribute by using semicolons to separate attributes.
The following syntax shows how to set values for multiple attributes:

`-OtherAttributes @{'Attribute1LDAPDisplayName'=value; 'Attribute2LDAPDisplayName'=value1,value2;...}`

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

Returns an object representing the item with which you're working. By default, this cmdlet does
not generate any output.

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

Specifies the X.500 path of the organizational unit (OU) or container where the new object is
created.

In many cases, a default value will be used for the **Path** parameter if no value is specified.
The rules for determining the default value are given below. Note that rules listed first are
evaluated first and once a default value can be determined, no further rules are evaluated.

In AD DS environments, a default value for **Path** is set in the following cases:

- If the cmdlet is run from an Active Directory PowerShell provider drive, the parameter is set to
  the current path of the provider drive.
- If the cmdlet has a default path, this is used.
  For example: in `New-ADUser`, the **Path** parameter defaults to the Users container.
- If none of the previous cases apply, the default value of **Path** is set to the default
  partition or naming context of the target domain.

In AD LDS environments, a default value for **Path** is set in the following cases:

- If the cmdlet is run from an Active Directory PowerShell provider drive, the parameter is set to
  the current path of the provider drive.
- If the cmdlet has a default path, this is used.
  For example: in `New-ADUser`, the **Path** parameter defaults to the Users container.
- If the target AD LDS instance has a default naming context, the default value of **Path** is set
  to the default naming context. To specify a default naming context for an AD LDS environment, set
  the `msDS-defaultNamingContext` property of the Active Directory directory service agent object
  (**nTDSDSA**) for the AD LDS instance.
- If none of the previous cases apply, the **Path** parameter doesn't take any default value.

Note: The Active Directory Provider cmdlets, such as `New-Item`, `Remove-Item`,
`Remove-ItemProperty`, `Rename-Item`, and `Set-ItemProperty`, also contain a **Path**
property. However, for the provider cmdlets, the **Path** parameter identifies the path of the
actual object and not the container as with the Active Directory cmdlets.

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

Specifies the accounts that can act on the behalf of users to services running as this managed
service account or group-managed service account. This parameter sets the
`msDS-AllowedToActOnBehalfOfOtherIdentity` attribute of the object.

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

Specifies the membership policy for systems that can use a group-managed service account. For a
service to run under a group managed service account, the system must be in the membership policy
of the account. This parameter sets the `msDS-GroupMSAMembership` attribute of a group-managed
service account object. This parameter should be set to the principals allowed to use this
group-managed service account.

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

Indicates that the cmdlet creates a group-managed service account that on success can be used by a
service for successful outbound authentication requests only. This allows creating a group managed
service account without the parameters required for successful inbound authentication.

```yaml
Type: SwitchParameter
Parameter Sets: RestrictedToOutboundAuthenticationOnly
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RestrictToSingleComputer

Indicates that the cmdlet creates a managed service account that can be used only for a single
computer. Managed service accounts that are linked to a single computer account were introduced in
Windows Server 2008 R2.

```yaml
Type: SwitchParameter
Parameter Sets: RestrictedToSingleComputer
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CreateDelegatedServiceAccount

Indicates that the cmdlet creates a delegated managed service account that be used for migration.
Delegated managed service accounts were introduced in Windows Server 2025.

```yaml
Type: SwitchParameter
Parameter Sets: Group
Aliases:

Required: False
Position: Named
Default value: none
Accept pipeline input: False
Accept wildcard characters: False
```

### -SamAccountName

Specifies the Security Account Manager (SAM) account name of the user, group, computer, or service
account. The maximum length of the description is 256 characters. To be compatible with older
operating systems, create a SAM account name that's 15 characters or less. This parameter sets the
**SAMAccountName** for an account object. The LDAP display name (**ldapDisplayName**) for this
property is sAMAccountName.

Note: If the specified **SAMAccountName** string doesn't end with a $ (dollar sign), one is
appended if necessary.

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

Specifies the Active Directory Domain Services (AD DS) instance to connect to, by providing one of
the following values for a corresponding domain name or directory server. The service may be any of
the following: Active Directory Lightweight Domain Services (AD LDS), AD DS, or Active Directory
snapshot instance.

Domain name values:

- Fully qualified domain name (FQDN)
- NetBIOS name

Directory server values:

- Fully qualified directory server name
- NetBIOS name
- Fully qualified directory server name and port

The default value for the *Server* parameter is determined by one of the following methods in the
order that they are listed:

- By using *Server* value from objects passed through the pipeline.
- By using the server information associated with the Active Directory PowerShell provider drive,
  when running under that drive.
- By using the domain of the computer running PowerShell.

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

Specifies the service principal names for the account. This parameter sets the
**ServicePrincipalNames** property of the account. The LDAP display name (**ldapDisplayName**) for
this property is servicePrincipalName. This parameter uses the following syntax to add remove,
replace or clear service principal name values.

To add values:

`-ServicePrincipalNames @{Add=value1,value2,...}`

To remove values:

`-ServicePrincipalNames @{Remove=value3,value4,...}`

To replace values:

`-ServicePrincipalNames @{Replace=value1,value2,...}`

To clear all values:

`-ServicePrincipalNames $Null`

You can specify more than one change by using a list separated by semicolons. For example, use the
following syntax to add and remove service principal names.

`@{Add=value1,value2,...};@{Remove=value3,value4,...}`

The operators are applied in the following sequence:

- Remove
- Add
- Replace

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

Indicates whether an account is trusted for Kerberos delegation. A service that runs under an
account that's trusted for Kerberos delegation can assume the identity of a client requesting the
service. This parameter sets the **TrustedForDelegation** property of an account object. This value
also sets the **ADS_UF_TRUSTED_FOR_DELEGATION** flag of the Active Directory User Account Control
attribute. The acceptable values for this parameter are:

- $False or 0
- $True or 1

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

Shows what would happen if the cmdlet runs. The cmdlet isn't run.

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

This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`,
`-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`,
`-Verbose`, `-WarningAction`, and `-WarningVariable`. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### None or Microsoft.ActiveDirectory.Management.ADServiceAccount

You can pipe a managed service account object that's a template for the new managed service
account object to the **Instance** parameter.

## OUTPUTS

### None or Microsoft.ActiveDirectory.Management.ADServiceAccount

This cmdlet returns the new managed service account object when the **PassThru** parameter.is
specified. By default, this cmdlet doesn't generate any output.

## NOTES

- This cmdlet doesn't work with AD LDS.
- This cmdlet doesn't work with an Active Directory snapshot.
- This cmdlet doesn't work with a read-only domain controller.
- This cmdlet requires that you create a Microsoft Group Key Distribution Service (GKDS) root key
  first to begin using group managed service accounts in your Active Directory deployment. For more
  information on how to create the GKDS root key using Windows PowerShell, see
  [Create the Key Distribution Services KDS Root Key](https://go.microsoft.com/fwlink/?LinkId=253584).

## RELATED LINKS

[Get-ADServiceAccount](./Get-ADServiceAccount.md)

[Install-ADServiceAccount](./Install-ADServiceAccount.md)

[Remove-ADServiceAccount](./Remove-ADServiceAccount.md)

[Set-ADServiceAccount](./Set-ADServiceAccount.md)

[Uninstall-ADServiceAccount](./Uninstall-ADServiceAccount.md)
