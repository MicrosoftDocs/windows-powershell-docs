---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/activedirectory/set-adaccountpassword?view=windowsserver2016-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-ADAccountPassword
---

# Set-ADAccountPassword

## SYNOPSIS
Modifies the password of an Active Directory account.

## SYNTAX

```
Set-ADAccountPassword [-WhatIf] [-Confirm] [-AuthType <ADAuthType>] [-Credential <PSCredential>]
 [-Identity] <ADAccount> [-NewPassword <SecureString>] [-OldPassword <SecureString>] [-Partition <String>]
 [-PassThru] [-Reset] [-Server <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-ADAccountPassword** cmdlet sets the password for a user, computer, or service account.

The *Identity* parameter specifies the Active Directory account to modify.

You can identify an account by its distinguished name, GUID, security identifier (SID) or security accounts manager (SAM) account name.
You can also set the *Identity* parameter to an object variable such as `$<localADAccountObject>`, or you can pass an object through the pipeline to the *Identity* parameter.
For example, you can use the **Search-ADAccount** cmdlet to retrieve an account object and then pass the object through the pipeline to the **Set-ADAccountPassword** cmdlet.
Similarly, you can use **Get-ADUser**, **Get-ADComputer**, or **Get-ADServiceAccount**, for standalone MSAs, cmdlets to retrieve account objects that you can pass through the pipeline to this cmdlet.

Note: Group MSAs cannot set password since they are changed at predetermined intervals.

For Active Directory Lightweight Directory Services (AD LDS) environments, the Partition parameter must be specified except in the following two conditions:

- The cmdlet is run from an Active Directory provider drive.
- A default naming context or partition is defined for the AD LDS environment. 

To specify a default naming context for an AD LDS environment, set the **msDS-defaultNamingContext** property of the Active Directory directory service agent (DSA) object (**nTDSDSA**) for the AD LDS instance.

## EXAMPLES

### Example 1: Set a password for a user account using a distinguished name
```
PS C:\> Set-ADAccountPassword -Identity 'CN=Elisa Daugherty,OU=Accounts,DC=Fabrikam,DC=com' -Reset -NewPassword (ConvertTo-SecureString -AsPlainText "p@ssw0rd" -Force)
```

This command sets the password of the user account with DistinguishedName CN=Elisa Daugherty,OU=Accounts,DC=Fabrikam,DC=com to p@ssw0rd.

### Example 2: Change a specified user's password
```
PS C:\> Set-ADAccountPassword -Identity elisada -OldPassword (ConvertTo-SecureString -AsPlainText "p@ssw0rd" -Force) -NewPassword (ConvertTo-SecureString -AsPlainText "qwert@12345" -Force)
```

This command sets the password of the user account with SamAccountName elisada to qwert@12345.
Using -NewPassword with a value, without providing an -OldPassword parameter value, will also reset the password.

### Example 3: Prompt a specified user to change their password
```
PS C:\> Set-ADAccountPassword -Identity EvanNa


Please enter the current password for 'CN=Evan Narvaez,CN=Users,DC=Fabrikam,DC=com'
Password:********** 
Please enter the desired password for 'CN=Evan Narvaez,CN=Users,DC=Fabrikam,DC=com'
Password:*********** 
Repeat Password:***********
```

This command sets the password of the user account with DistinguishedName CN=Evan Narvaez,CN=Users,DC=Fabrikam,DC=com.
The cmdlet prompts you for old and new passwords.

### Example 4: Prompt a user for a new password that is stored in a temporary variable
```
PS C:\> $NewPassword = (Read-Host -Prompt "Provide New Password" -AsSecureString) 
PS C:\> Set-ADAccountPassword -Identity DavidChe -NewPassword $NewPassword -Reset
Provide New Password: **********
```

This command prompts the user for a new password that is stored in a temporary variable named $NewPassword, then uses it to reset the password for the user account with SamAccountName DavidChe.

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

### -Identity
Specifies an Active Directory user object by providing one of the following property values.
The identifier in parentheses is the Lightweight Directory Access Protocol (LDAP) display name for the attribute.
The acceptable values for this parameter are:

- A distinguished name
- A GUID (objectGUID) 
- A security identifier (objectSid) 
- A SAM account name (sAMAccountName)

The cmdlet searches the default naming context or partition to find the object.
If two or more objects are found, the cmdlet returns a non-terminating error.

This parameter can also get this object through the pipeline or you can set this parameter to an object instance.

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

### -NewPassword
Specifies a new password value.
This value is stored as an encrypted string.

```yaml
Type: SecureString
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OldPassword
Specifies the most recent password value.
This value is processed as an encrypted string.

```yaml
Type: SecureString
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

In Active Directory Domain Services environments, a default value for **Partition** is set in the following cases: 

- If the *Identity* parameter is set to a distinguished name, the default value of *Partition* is automatically generated from this distinguished name.
- If running cmdlets from an Active Directory provider drive, the default value of *Partition* is automatically generated from the current path in the drive. 
- If none of the previous cases apply, the default value of *Partition* is set to the default partition or naming context of the target domain.

In AD LDS environments, a default value for *Partition* is set in the following cases:

- If the *Identity* parameter is set to a distinguished name, the default value of  is automatically generated from this distinguished name. 
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

### -Reset
Specifies to reset the password on an account.
When you use this parameter, you must set the *NewPassword* parameter.
You do not need to specify the *OldPassword* parameter.

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

### -Server
Specifies the Active Directory Domain Services instance to connect to, by providing one of the following values for a corresponding domain name or directory server.
The service may be any of the following:  Active Directory Lightweight Domain Services, Active Directory Domain Services or Active Directory snapshot instance.

Domain name values:

- Fully qualified domain name (FQDN)
- NetBIOS name

Directory server values: 

- Fully qualified directory server name
- NetBIOS name
- Fully qualified directory server name and port

The default value for the *Server* parameter is determined by one of the following methods in the order that they are listed:

- By using *Server* value from objects passed through the pipeline.
- By using the server information associated with the Active Directory provider drive, when running under that drive.
- By using the domain of the computer running Windows PowerShell.

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
* This cmdlet does not work with a read-only domain controller. This cmdlet does not work when connected to global catalog port.

## RELATED LINKS

[Get-ADComputer](./Get-ADComputer.md)

[Get-ADServiceAccount](./Get-ADServiceAccount.md)

[Get-ADUser](./Get-ADUser.md)

[Search-ADAccount](./Search-ADAccount.md)

[AD DS Administration Cmdlets in Windows PowerShell](./activedirectory.md)

