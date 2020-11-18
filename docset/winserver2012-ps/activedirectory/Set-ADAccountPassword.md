---
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
ms.assetid: 3FB5BEE8-B432-4FB1-B5DD-3FC2209D7191
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
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
The Set-ADAccountPassword cmdlet sets the password for a user, computer or service account.

The Identity parameter specifies the Active Directory account to modify.

You can identify an account by its distinguished name (DN), GUID, security identifier (SID) or security accounts manager (SAM) account name.
You can also set the Identity parameter to an object variable such as $\<localADAccountObject\>, or you can pass an object through the pipeline to the Identity parameter.
For example, you can use the Search-ADAccount cmdlet to retrieve an account object and then pass the object through the pipeline to the Set-ADAccountPassword cmdlet.
Similarly, you can use Get-ADUser, Get-ADComputer or Get-ADServiceAccount, for standalone MSAs, cmdlets to retrieve account objects that you can pass through the pipeline to this cmdlet.

Note: Group MSAs cannot set password since they are changed at predetermined intervals.

For Active Directory Lightweight Directory Services (AD LDS) environments, the Partition parameter must be specified except in the following two instances:

-The cmdlet is run from an Active Directory provider drive.

-A default naming context or partition is defined for the AD LDS environment.
To specify a default naming context for an AD LDS environment, set the msDS-defaultNamingContext property of the Active Directory directory service agent (DSA) object (nTDSDSA) for the AD LDS instance.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Set-ADAccountPassword 'CN=Jeremy Los,OU=Accounts,DC=Fabrikam,DC=com' -Reset -NewPassword (ConvertTo-SecureString -AsPlainText "p@ssw0rd" -Force)
```

Description

-----------

Sets the password of the user account with DistinguishedName: 'CN=Jeremy Los,OU=Accounts,DC=Fabrikam,DC=com' to 'p@ssw0rd'.

### -------------------------- EXAMPLE 2 --------------------------
```
C:\PS>Set-ADAccountPassword -Identity tmakovec -OldPassword (ConvertTo-SecureString -AsPlainText "p@ssw0rd" -Force) -NewPassword (ConvertTo-SecureString -AsPlainText "qwert@12345" -Force)
```

Description

-----------

Sets the password of the user account with SamAccountName: tmakovec to 'qwert@12345'.
Using -NewPassword with a value, without providing an -OldPassword parameter value, will also reset the password.

### -------------------------- EXAMPLE 3 --------------------------
```
C:\PS>Set-ADAccountPassword -Identity saradavi

Please enter the current password for 'CN=Sara Davis,CN=Users,DC=Fabrikam,DC=com'
Password:**********
Please enter the desired password for 'CN=Sara Davis,CN=Users,DC=Fabrikam,DC=com'
Password:***********
Repeat Password:***********
```

Description

-----------

Sets the password of the user account with DistinguishedName: 'CN=Sara Davis,CN=Users,DC=Fabrikam,DC=com' (user is prompted for old and new password).

### -------------------------- EXAMPLE 4 --------------------------
```
C:\PS>$newPassword = (Read-Host -Prompt "Provide New Password" -AsSecureString); Set-ADAccountPassword -Identity mollyd -NewPassword $newPassword -Reset

Provide New Password: **********
```

Description

-----------

Prompts the user for a new password that is stored in a temporary variable named $newPassword, then uses it to reset the password for the user account with SamAccountName: mollyd.

### -------------------------- EXAMPLE 5 --------------------------
```
PS C:\Users\administrator.FABRIKAM> set-adaccountpassword "CN=Molly Dempsey,OU=AccountDeptOU,DC=AppNC" -server "dsp13a24:60000"


Please enter the current password for 'CN=mollyd,OU=AccountDeptOU,DC=AppNC'
Password:**********
Please enter the desired password for 'CN=mollyd,OU=AccountDeptOU,DC=AppNC'
Password:**********
Repeat Password:**********
```

Description

-----------

Sets the password of the user account with DistinguishedName: 'CN=mollyd,OU=AccountDeptOU,DC=AppNC' in the AD LDS instance: "dsp13a24:60000" (user is prompted for old and new password).

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

The following example shows how to set this parameter.
This command will prompt you and wait for a password.

-NewPassword (Read-Host -AsSecureString "New Password")

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
This value is processed as a encrypted string.

The following example shows how to set this parameter.
This command will prompt you and wait for a password.

-OldPassword  (Read-Host -AsSecureString "Old Password")

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

### -Reset
Specifies to reset the password on an account.
When you use this parameter, you must set the NewPassword parameter.
You do not need to specify the OldPassword parameter.

The following example shows how to use this parameter to set a new password.
This command will prompt you then wait for a password.

-Reset -NewPassword (Read-Host -AsSecureString "New Password")

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

### -WhatIf
Shows what would happen if the cmdlet runs.
The WhatIf switch causes the command to simulate its results. Using this switch allows you to view changes that would occur, without having to commit those changes.

> [!NOTE]
> -WhatIf command functionality was first fixed in the Windows 1607 RSAT package. If using an RSAT package prior to the Windows 1607 RSAT package, this parameter will not function. 
 
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

[Search-ADAccount](./Search-ADAccount.md)

