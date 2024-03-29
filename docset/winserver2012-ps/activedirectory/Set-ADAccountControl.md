---
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
online version: https://learn.microsoft.com/powershell/module/activedirectory/set-adaccountcontrol?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-ADAccountControl

## SYNOPSIS
Modifies user account control (UAC) values for an Active Directory account.

## SYNTAX

```
Set-ADAccountControl [-WhatIf] [-Confirm] [-AccountNotDelegated <Boolean>]
 [-AllowReversiblePasswordEncryption <Boolean>] [-AuthType <ADAuthType>] [-CannotChangePassword <Boolean>]
 [-Credential <PSCredential>] [-DoesNotRequirePreAuth <Boolean>] [-Enabled <Boolean>]
 [-HomedirRequired <Boolean>] [-Identity] <ADAccount> [-MNSLogonAccount <Boolean>] [-Partition <String>]
 [-PassThru] [-PasswordNeverExpires <Boolean>] [-PasswordNotRequired <Boolean>] [-Server <String>]
 [-TrustedForDelegation <Boolean>] [-TrustedToAuthForDelegation <Boolean>] [-UseDESKeyOnly <Boolean>]
 [<CommonParameters>]
```

## DESCRIPTION
The Set-ADAccountControl cmdlet modifies the user account control (UAC) values for an Active Directory user or computer account.
UAC values are represented by cmdlet parameters.
For example, set the PasswordExpired parameter to change whether an account is expired and to modify the ADS_UF_PASSWORD_EXPIRED UAC value.

The Identity parameter specifies the Active Directory account to modify.

You can identify an account by its distinguished name (DN), GUID, security identifier (SID) or security accounts manager (SAM) account name.
You can also set the Identity parameter to an object variable such as $\<localADAccountObject\>, or you can pass an account object through the pipeline to the Identity parameter.
For example, you can use the Search-ADAccount cmdlet to retrieve an account object and then pass the object through the pipeline to the Set-ADAccountControl cmdlet.
Similarly, you can use Get-ADUser, Get-ADComputer or Get-ADServiceAccount cmdlets to retrieve account objects that you can pass through the pipeline to this cmdlet.

For AD LDS environments, the Partition parameter must be specified except in the following two conditions:

-The cmdlet is run from an Active Directory provider drive.

-A default naming context or partition is defined for the AD LDS environment.
To specify a default naming context for an AD LDS environment, set the msDS-defaultNamingContext property of the Active Directory directory service agent (DSA) object (nTDSDSA) for the AD LDS instance.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Set-ADAccountControl JimmyBi -PasswordNotRequired $false
```

Description

-----------

Sets the flag on userAccountControl to make sure that a password is required for logon.

### -------------------------- EXAMPLE 2 --------------------------
```
C:\PS>Set-ADAccountControl 'CN=Jimmy Bischoff,OU=HumanResources,OU=UserAccounts,DC=FABRIKAM,DC=COM' -CannotChangePassword $true
```

Description

-----------

Sets the security descriptor of the user to make sure they cannot change their own password.

### -------------------------- EXAMPLE 3 --------------------------
```
C:\PS>Set-ADAccountControl SQLAdmin1 -AccountNotDelegated $true
```

Description

-----------

Sets the flag on userAccountControl to make sure that the account cannot be delegated.

### -------------------------- EXAMPLE 4 --------------------------
```
C:\PS>Set-ADAccountControl 'CN=IIS01 SvcAccount,OU=ServiceAccounts,OU=Managed,DC=FABRIKAM,DC=COM' -TrustedToAuthForDelegation $true
```

Description

-----------

Sets the flag on userAccountControl to make sure that the account is now trusted to authenticate for delegation.

### -------------------------- EXAMPLE 5 --------------------------
```
C:\PS>Set-ADAccountControl -Identity "FABRIKAM-SRV1" -TrustedForDelegation $true
```

Description

-----------

The specified computer is now set to be trusted for delegation.

### -------------------------- EXAMPLE 6 --------------------------
```
C:\PS>Set-ADAccountControl DickBe -PasswordNeverExpires $true
```

Description

-----------

Sets the password of the user to never expire.

### -------------------------- EXAMPLE 7 --------------------------
```
C:\PS>Set-ADAccountControl 'CN=Dick Beekman,OU=HumanResources,OU=UserAccounts,DC=FABRIKAM,DC=COM' -HomedirRequired $true
```

Description

-----------

Sets the user account to require a Home Directory.

## PARAMETERS

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
Parameter Sets: (All)
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
Modifies the ability of an account to change its password.
To disallow password change by the account set this to $true..
This parameter changes the Boolean value of the CannotChangePassword property of an account.

The following example shows how to specify the PasswordCannotChange parameter.

-CannotChangePassword $false

```yaml
Type: Boolean
Parameter Sets: (All)
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

### -DoesNotRequirePreAuth
Specifies whether Kerberos pre-authentication is required to logon using the user or computer account.
This parameter sets the ADS_UF_DONT_REQUIRE_PREAUTH flag of the Active Directory User Account Control (UAC) attribute.
Possible values for this parameter include:

$false or 0

$true or 1

The following example shows how to set this parameter so that Kerberos pre-authentication is required to logon to the account.

-DoesNotRequirePreAuth $false

```yaml
Type: Boolean
Parameter Sets: (All)
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
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HomedirRequired
Specifies whether a home directory is required for the account.
This parameter sets the ADS_UF_HOMEDIR_REQUIRED flag of the Active Directory User Account Control (UAC) attribute.
Possible values for this parameter include:

$false or 0

$true or 1

The following example shows how to set this parameter so that a home directory is not required for the account.

-HomedirRequired $false

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Identity
Distinguished Name

Example: CN=SaraDavis ,CN=Users,DC=corp,DC=contoso,DC=com

GUID (objectGUID)

Example: 599c3d2e-f72d-Specifies an Active Directory account object by providing one of the following property values.
The identifier in parentheses is the LDAP display name for the attribute.4d20-8a88-030d99495f20

Security Identifier (objectSid)

Example: S-1-5-21-3165297888-301567370-576410423-1103

SAM Account Name (sAMAccountName)

Example: saradavis

The cmdlet searches the default naming context or partition to find the object.
If two or more objects are found, the cmdlet returns a non-terminating error.

This parameter can also get this object through the pipeline or you can set this parameter to an account object instance.

Derived types such as the following are also accepted:

Microsoft.ActiveDirectory.Management.ADUser

Microsoft.ActiveDirectory.Management.ADComputer

Microsoft.ActiveDirectory.Management.ADServiceAccount

This example shows how to set the parameter to a distinguished name.

-Identity "CN=saradavis,CN=Users,DC=corp,DC=contoso,DC=com"

This example shows how to set this parameter to an account object instance named "accountInstance".

-Identity $accountInstance

```yaml
Type: ADAccount
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -MNSLogonAccount
Specifies whether the account is a Majority Node Set (MNS) logon account.
This parameter also sets the ADS_UF_MNS_LOGON_ACCOUNT flag of the Active Directory User Account Control (UAC) attribute.
Possible values for this parameter include:

$false or 0

$true or 1

You can use MNS logon accounts to configure a multi-node cluster without using a shared disk drive.

The following example shows how to set this parameter to identify this account as an MNS account.

-MSNLogonAccount $true

```yaml
Type: Boolean
Parameter Sets: (All)
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
Parameter Sets: (All)
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
Accept pipeline input: False
Accept wildcard characters: False
```

### -TrustedToAuthForDelegation
Specifies whether an account is enabled for delegation.
When this parameter is set to true, a service running under such an account can impersonate a client on other remote servers on the network.
This parameter sets the ADS_UF_TRUSTED_TO_AUTHENTICATE_FOR_DELEGATION flag of the Active Directory User Account Control attribute.
Possible values for this parameter are:

$false or 0

$true or 1

The following example shows how to set this parameter so that the account is enabled for delegation.

-TrustedToAuthForDelegation $true

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseDESKeyOnly
Specifies whether an account is restricted to use only Data Encryption Standard (DES) encryption types for keys.
This parameter sets the

ADS_UF_USE_DES_KEY_ONLY flag of the Active Directory User Account Control attribute.
Possible values for this parameter are:

$false or 0

$true or 1

The following example shows how to set this parameter so that an account must use DES encryption types for keys.

-UseDESKeyOnly $true

```yaml
Type: Boolean
Parameter Sets: (All)
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

### Microsoft.ActiveDirectory.Management.ADAccount
An account object is received by the Identity parameter.

Derived types, such as the following are also accepted:

Microsoft.ActiveDirectory.Management.ADUser

Microsoft.ActiveDirectory.Management.ADComputer

Microsoft.ActiveDirectory.Management.ADServiceAccount

## OUTPUTS

### None

## NOTES
* This cmdlet does not work with an Active Directory Snapshot.

  This cmdlet does not work with a read-only domain controller.

  This cmdlet does not work when connected to Global Catalog port.

## RELATED LINKS

[Get-ADComputer](./Get-ADComputer.md)

[Get-ADServiceAccount](./Get-ADServiceAccount.md)

[Get-ADUser](./Get-ADUser.md)

