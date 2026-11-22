---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/activedirectory/set-adaccountcontrol?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-ADAccountControl
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
The **Set-ADAccountControl** cmdlet modifies the user account control (UAC) values for an Active Directory user or computer account.
UAC values are represented by cmdlet parameters.
For example, set the *PasswordNeverExpires* parameter to change whether an account password could expire and to modify the **ADS_UF_DONT_EXPIRE_PASSWD** UAC value.

The *Identity* parameter specifies the Active Directory account to modify.

You can identify an account by its distinguished name, GUID, security identifier (SID), or security accounts manager (SAM) account name.
You can also set the *Identity* parameter to an object variable such as `$<localADAccountObject>`, or you can pass an account object through the pipeline to the *Identity* parameter.
For example, you can use the **Search-ADAccount** cmdlet to retrieve an account object and then pass the object through the pipeline to the **Set-ADAccountControl** cmdlet.
Similarly, you can use **Get-ADUser**, **Get-ADComputer**, or **Get-ADServiceAccount** cmdlets to retrieve account objects that you can pass through the pipeline to this cmdlet.

For Active Directory Lightweight Directory Services (AD LDS) environments, the *Partition* parameter must be specified except in the following two conditions:

- The cmdlet is run from an Active Directory provider drive.
- A default naming context or partition is defined for the AD LDS environment.

To specify a default naming context for an AD LDS environment, set the **msDS-defaultNamingContext** property of the Active Directory directory service agent (DSA) object (**nTDSDSA**) for the AD LDS instance.

## EXAMPLES

### Example 1: Require that a user use a password to logon
```
PS C:\> Set-ADAccountControl -Identity ElisaD -PasswordNotRequired $False
```

This command sets the flag on userAccountControl to make sure that a password is required for logon.

### Example 2: Disable change password on a user account
```
PS C:\> Set-ADAccountControl -Identity 'CN=Elisa Daugherty,OU=HumanResources,OU=UserAccounts,DC=FABRIKAM,DC=COM' -CannotChangePassword $True
```

This command sets the security descriptor of the user to make sure they cannot change their own password.

### Example 3: Disable delegation on a user account
```
PS C:\> Set-ADAccountControl -Identity SQLAdmin1 -AccountNotDelegated $True
```

This command sets the flag on userAccountControl to make sure that the account cannot be delegated.

### Example 4: Set a user account to be trusted to authenticate for delegation
```
PS C:\> Set-ADAccountControl -Identity 'CN=IIS01 SvcAccount,OU=ServiceAccounts,OU=Managed,DC=FABRIKAM,DC=COM' -TrustedToAuthForDelegation $True
```

This command sets the flag on userAccountControl to make sure that the account is now trusted to authenticate for delegation.

### Example 5: Set a specified computer to be trusted for delegation
```
PS C:\> Set-ADAccountControl -Identity "FABRIKAM-SRV1" -TrustedForDelegation $True
```

This command sets specified computer to be trusted for delegation.

### Example 6: Set a user password to never expire
```
PS C:\> Set-ADAccountControl -Identity EvanNa -PasswordNeverExpires $True
```

This command sets the password of the user to never expire.

### Example 7: Set a user account to require a home directory
```
PS C:\> Set-ADAccountControl -Identity 'CN=Evan Narvaez,OU=HumanResources,OU=UserAccounts,DC=FABRIKAM,DC=COM' -HomedirRequired $True
```

This command sets the user account to require a Home Directory.

## PARAMETERS

### -AccountNotDelegated
Indicates whether the security context of the user is delegated to a service.
When this parameter is set to true, the security context of the account is not delegated to a service even when the service account is set as trusted for Kerberos delegation.
This parameter sets the **AccountNotDelegated** property for an Active Directory account.
This parameter also sets the **ADS_UF_NOT_DELEGATED** flag of the Active Directory UAC attribute.

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
Indicates whether reversible password encryption is allowed for the account.
This parameter sets the **AllowReversiblePasswordEncryption** property of the account.
This parameter also sets the **ADS_UF_ENCRYPTED_TEXT_PASSWORD_ALLOWED** flag of the Active Directory UAC attribute.

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

### -CannotChangePassword
Indicates whether an account can change its password.
To disallow password change by the account set this to $True.
This parameter changes the Boolean value of the **CannotChangePassword** property of an account.

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

### -DoesNotRequirePreAuth
Indicates whether Kerberos pre-authentication is required to logon using the user or computer account.
This parameter sets the **ADS_UF_DONT_REQUIRE_PREAUTH** flag of the Active Directory UAC attribute.
The acceptable values for this parameter are:

- $False or 0
- $True or 1

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
Specifies whether an account is enabled.
An enabled account requires a password.
This parameter sets the **Enabled** property for an account object.
This parameter also sets the **ADS_UF_ACCOUNTDISABLE** flag of the Active Directory UAC attribute.The acceptable values for this parameter are:

- $False or 0
- $True or 1

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
Indicates whether a home directory is required for the account.
This parameter sets the **ADS_UF_HOMEDIR_REQUIRED** flag of the Active Directory UAC attribute.The acceptable values for this parameter are:

- $False or 0
- $True or 1

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
Specifies an Active Directory account object by providing one of the following property values.
The identifier in parentheses is the Lightweight Directory Access Protocol (LDAP) display name for the attribute.
The acceptable values for this parameter are:

- A distinguished name
- A GUID (objectGUID)
- A Security Identifier (objectSid)
- A SAM Account Name (sAMAccountName)

The cmdlet searches the default naming context or partition to find the object.
If two or more objects are found, the cmdlet returns a non-terminating error.

This parameter can also get this object through the pipeline or you can set this parameter to an account object instance.

Derived types such as the following are also accepted:

- **Microsoft.ActiveDirectory.Management.ADServiceAccount**
- **Microsoft.ActiveDirectory.Management.ADComputer**
- **Microsoft.ActiveDirectory.Management.ADUser**

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
Indicates whether the account is a Majority Node Set (MNS) logon account.
This parameter also sets the **ADS_UF_MNS_LOGON_ACCOUNT** flag of the Active Directory UAC attribute.
The acceptable values for this parameter are:

- $False or 0
- $True or 1

You can use MNS logon accounts to configure a multi-node cluster without using a shared disk drive.

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
The cmdlet searches this partition to find the object defined by the *Identity* parameter.

In many cases, a default value is used for the *Partition* parameter if no value is specified.
The rules for determining the default value are given below.
Note that rules listed first are evaluated first and once a default value can be determined, no further rules are evaluated.

In Active Directory Domain Services (AD DS) environments, a default value for *Partition* is set in the following cases:

- If the *Identity* parameter is set to a distinguished name, the default value of *Partition* is automatically generated from this distinguished name.
- If running cmdlets from an Active Directory provider drive, the default value of *Partition* is automatically generated from the current path in the drive.
- If none of the previous cases apply, the default value of *Partition* is set to the default partition or naming context of the target domain.

In AD LDS environments, a default value for *Partition* is set in the following cases:

- If the *Identity* parameter is set to a distinguished name, the default value of *Partition* is automatically generated from this distinguished name.
- If running cmdlets from an Active Directory provider drive, the default value of *Partition* is automatically generated from the current path in the drive.
- If the target AD LDS instance has a default naming context, the default value of *Partition* is set to the default naming context.
To specify a default naming context for an AD LDS environment, set the **msDS-defaultNamingContext** property of the Active Directory directory service agent object (**nTDSDSA**) for the AD LDS instance.
- If none of the previous cases apply, the *Partition* parameter will not take any default value.

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
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

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
Indicates whether the password of an account can expire.
This parameter sets the **PasswordNeverExpires** property of an account object.
This parameter also sets the **ADS_UF_DONT_EXPIRE_PASSWD** flag of the Active Directory UAC attribute.
The acceptable values for this parameter are:

- $False or 0
- $True or 1

Note: This parameter cannot be set to $True for an account that also has the **ChangePasswordAtLogon** property set to $True.

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
Indicates whether the account requires a password.
This parameter sets the **PasswordNotRequired** property of an account, such as a user or computer account.
This parameter also sets the **ADS_UF_PASSWD_NOTREQD** flag of the Active Directory UAC attribute.
The acceptable values for this parameter are:

- $False or 0
- $True or 1

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
The service may be any of the following: Active Directory Lightweight Domain Services, Active Directory Domain Services or Active Directory snapshot instance.

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

### -TrustedForDelegation
Indicates whether an account is trusted for Kerberos delegation.
A service that runs under an account that is trusted for Kerberos delegation can assume the identity of a client requesting the service.
This parameter sets the **TrustedForDelegation** property of an account object.
This value also sets the **ADS_UF_TRUSTED_FOR_DELEGATION** flag of the Active Directory UAC attribute.
The acceptable values for this parameter are:

- $False or 0
- $True or 1

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
Indicates whether an account is enabled for delegation.
When this parameter is set to true, a service running under such an account can impersonate a client on other remote servers on the network.
This parameter sets the **ADS_UF_TRUSTED_TO_AUTHENTICATE_FOR_DELEGATION** flag of the Active Directory UAC attribute.
The acceptable values for this parameter are:

- $False or 0
- $True or 1

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
Indicates whether an account is restricted to use only Data Encryption Standard encryption types for keys.
This parameter sets the **ADS_UF_USE_DES_KEY_ONLY** flag of the Active Directory UAC attribute.
The acceptable values for this parameter are:

- $False or 0
- $True or 1

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.ActiveDirectory.Management.ADAccount
An account object is received by the *Identity* parameter.

Derived types, such as the following are also accepted:

- **Microsoft.ActiveDirectory.Management.ADUser**
- **Microsoft.ActiveDirectory.Management.ADComputer**
- **Microsoft.ActiveDirectory.Management.ADServiceAccount**

## OUTPUTS

### None

## NOTES
* This cmdlet does not work with an Active Directory snapshot.
* This cmdlet does not work with a read-only domain controller.
* This cmdlet does not work when connected to global catalog port.

## RELATED LINKS

[Get-ADComputer](./Get-ADComputer.md)

[Get-ADServiceAccount](./Get-ADServiceAccount.md)

[Get-ADUser](./Get-ADUser.md)

[AD DS Administration Cmdlets in Windows PowerShell](./activedirectory.md)

